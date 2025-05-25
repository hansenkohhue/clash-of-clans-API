const express = require('express');
const axios = require('axios');
const cors = require('cors');

const app = express();
const port = process.env.PORT || 3000;

// Replace this with your actual Clash of Clans API token
const COC_API_TOKEN = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiIsImtpZCI6IjI4YTMxOGY3LTAwMDAtYTFlYi03ZmExLTJjNzQzM2M2Y2NhNSJ9.eyJpc3MiOiJzdXBlcmNlbGwiLCJhdWQiOiJzdXBlcmNlbGw6Z2FtZWFwaSIsImp0aSI6IjIxM2E3NWQxLWM2OTgtNDMzOS1hYjM5LTEyNWFmMTNkMmZkYSIsImlhdCI6MTc0ODExNzU5Mywic3ViIjoiZGV2ZWxvcGVyL2FjMDlmOTM5LWIzYjctNTBlYS1hZTliLWFkY2E0MDBjZDFjNiIsInNjb3BlcyI6WyJjbGFzaCJdLCJsaW1pdHMiOlt7InRpZXIiOiJkZXZlbG9wZXIvc2lsdmVyIiwidHlwZSI6InRocm90dGxpbmcifSx7ImNpZHJzIjpbIjIwOC42Ny4yMjIuMjIyIl0sInR5cGUiOiJjbGllbnQifV19.avdtJdn1jr8uJA0SLU2BpHKtu45xkHiGHKo62fSIQJ5vxLQOsYCWDbFO1fEKK69nM_t6YjUuymW9g6olMvqSAQ';

app.use(cors());

app.get('/player/:tag', async (req, res) => {
  const tag = req.params.tag.replace('#', '%23'); // encode #
  const url = `https://api.clashofclans.com/v1/players/${tag}`;

  try {
    const response = await axios.get(url, {
      headers: {
        Authorization: COC_API_TOKEN
      }
    });
    res.json(response.data);
  } catch (error) {
    console.error(error?.response?.data || error);
    res.status(500).json({ error: 'Failed to fetch player data' });
  }
});

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
