# Travel Memory

Assignment 2 deployment by Aditya Verma. The MERN application is deployed on two EC2 instances across Availability Zones, behind an AWS Application Load Balancer, with Cloudflare DNS and ACM HTTPS.

- Application: Travel Memory App
- [Deployment report and screenshots](docs/deployment.md)
- [Architecture preview](image.png)
- [Nginx configuration](deploy/travelmemory.nginx.conf) and [systemd service](deploy/travelmemory-backend.service)

Original application source from [UnpredictablePrashant/TravelMemory](https://github.com/UnpredictablePrashant/TravelMemory); the original [license](LICENSE) is retained. The instructions below describe local development. The deployment report describes production configuration on backend port **3000** with frontend API URL **`/api`**.

`.env` file to work with the backend after creating a database in mongodb: 

```
MONGO_URI='ENTER_YOUR_URL'
PORT=3001
```

Data format to be added: 

```json
{
{
  "_id": {
    "$oid": "6af9cf18f57fa3a60f0c3422"
  },
  "tripName": "India",
  "startDateOfJourney": "2026-11-12",
  "endDateOfJourney": "2026-11-13",
  "nameOfHotels": "Vastu",
  "placesVisited": "Mumbai",
  "totalCost": 23220,
  "tripType": "business",
  "experience": "wow",
  "shortDescription": "Business",
  "featured": true,
  "createdAt": {
    "$date": "2026-11-15T15:26:16.556Z"
  },
  "updatedAt": {
    "$date": "2026-11-15T15:26:16.556Z"
  },
  "__v": 0
}
}
```


For frontend, you need to create `.env` file and put the following content (remember to change it based on your requirements):
```bash
REACT_APP_BACKEND_URL=http://localhost:3001
```

## How to run BE

Note: Make sure you have the .env file already added
```bash
cd backend
npm install
node index.js
```

## How to run FE
Note: Make sure you have the .env file already added
```bash
cd frontend
npm install
npm start
```
