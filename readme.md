# Proxy API Service

Welcome to the **Proxy API Service**! This API allows clients to retrieve a list of working SOCKS5 proxies from multiple sources. The service continuously fetches, tests, and maintains an up-to-date list of reliable proxies to ensure optimal performance and availability.

**Base URL:** [https://proxies.aleph.wtf/](https://proxies.aleph.wtf/)

## Features

- **Reliable Proxies:** Continuously tested proxies to ensure reliability.
- **Asynchronous Testing:** Fast and efficient proxy validation.
- **Automatic Updates:** Refreshes the proxy list every 10 minutes.
- **Simple and Flexible API:** Retrieve a single proxy or multiple proxies as needed.
- **Comprehensive Documentation:** Available at `/docs` for easy access.

## API Endpoints

### 1. Get Proxies

**Endpoint:** `GET /api/proxy`

Retrieve a list of working SOCKS5 proxies.

#### Query Parameters

| Parameter | Type    | Description                                                                                                                                                           |
| --------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `count`   | Integer | *(Optional)* Specifies the number of proxies to retrieve. Defaults to 1. If the requested count exceeds the available proxies, the API returns the maximum available. |

#### Responses

- **200 OK**

  Successfully retrieved the requested proxies.

  ```json
  {
    "proxies": [
      {
        "ip": "192.252.220.92",
        "port": "17328",
        "country": "United States"
      },
      {
        "ip": "192.111.137.37",
        "port": "18762",
        "country": "Canada"
      }
    ]
  }
  ```

- **503 Service Unavailable**

  No working proxies are available at the moment.

  ```json
  {
    "error": "No working proxies available. Please try again later."
  }
  ```

### 2. Health Check

**Endpoint:** `GET /health`

Check the health status of the Proxy API server.

#### Responses

- **200 OK**

  The server is running and healthy.
  ```
  OK
  ```

## Usage Examples

### Retrieve a Single Proxy

**Request:**

```
GET https://proxies.aleph.wtf/api/proxy
```

**Response:**

```json
{
  "proxies": [
    {
      "ip": "176.117.237.132",
      "port": "1080",
      "country": "Unknown"
    }
  ]
}
```

### Retrieve Multiple Proxies

**Request:**

```
GET https://proxies.aleph.wtf/api/proxy?count=5
```

**Response:**

```json
{
  "proxies": [
    {
      "ip": "192.252.220.92",
      "port": "17328",
      "country": "United States"
    },
    {
      "ip": "192.111.137.37",
      "port": "18762",
      "country": "Canada"
    },
    {
      "ip": "192.111.130.5",
      "port": "17002",
      "country": "Canada"
    },
    {
      "ip": "192.111.138.29",
      "port": "4145",
      "country": "Canada"
    },
    {
      "ip": "192.111.137.34",
      "port": "18765",
      "country": "Canada"
    }
  ]
}
```

### Health Check

**Request:**

```
GET https://proxies.aleph.wtf/health
```

**Response:**

```
OK
```

## Documentation

For detailed information about the API endpoints, usage examples, and other functionalities, please refer to the [API Documentation](https://proxies.aleph.wtf/docs).

## Contact

Follow me on [X (Formerly known as Twitter)](https://twitter.com/hey_itsmyturn)

---


