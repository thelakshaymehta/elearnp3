import sys
import base64
import json

def decode_payload(token):
    if not token.startswith('S0.'):
        return 'Not an OAuth token'
    
    payload = token.split('.')[1]
    decoded_data = base64.b64decode(payload.replace('@', '=').replace('_', '+').replace(',', '&'))
    
    try:
        # Attempt to format the decoded data as JSON
        formatted_data = json.dumps(json.loads(decoded_data), indent=4)
    except json.JSONDecodeError:
        # If it's not valid JSON, return the raw decoded data
        formatted_data = decoded_data.decode('utf-8')
    
    return formatted_data

if __name__ == '__main__':
    print(decode_payload(sys.argv[1]))
