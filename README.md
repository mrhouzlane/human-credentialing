# Human Credentialing API 

## TL;DR:

The Human Credentialing project aims to verify and associate online credentials with a wallet address, streamlining the job application process on the HUMAN Protocol. Credentials can be imported from platforms like GitHub and Fiverr for the moment. Once verified, these credentials are signed and stored on the [**Ceramic network**](https://ceramic.network/). Although they can be accessed by any Ceramic user, their continuous availability depends on pinning them to a Ceramic node.

For developers, there's a local setup using Docker, enabling them to test and develop locally. The interface, available at https://cred.linkedtrust.us/ , allows users to input and sign their credentials. By using the provided API, one can retrieve the stored credentials for a specific wallet address. This project's potential lies in its integration with [HUMAN Protocol](https://www.humanprotocol.org/) job matchers, providing a seamless experience for job seekers and employers alike. Feedback and contributions are encouraged to refine and improve the platform.


## How it is made

### Technologies Used
   
   - #### Ceramic
      - 

## Getting started

### Prerequisites

**Docker** : This project requires Docker for local setup. If you haven't already installed Docker, you can refer to the official Docker installation guide at https://docs.docker.com/.

### Launch Docker Environment: 

```docker compose -f docker-compose.dev.yaml up ``` 

## Development

### Github credentials 

- Navigate to http://localhost:3000/
- Click the provided button to authenticate with your GitHub account.
- Your public GitHub information will be fetched and stored in composedb. This data will be displayed on the page.
- For subsequent visits to http://localhost:3002/, the page will automatically retrieve and display the stored information after MetaMask authentication.

### Fiverr credentials 

- Click on Add your Fiverr ratings to navigate to the Fiverr page.
- Use the Get a token button to generate a token.
- Copy the generated token and paste it in your Fiverr description to collect your Fiverr ratings and related information.

### Direct Updates from Other Platforms:

- Visit http://localhost:3000/cred/platform.
- Obtain an API key by specifying the platform's name.
- This API key should be used as an x-api-key header when you want to update user reviews. 


## API Endpoints

Here is the list of currently available API endpoints:

```
{
   "Apis"{
   "git profile" : "http://localhost:3007/get-github-profile/{user_id (wallet adress)}",
   "fiverr profile" : "http://localhost:3007/fiverr-profile/{user_id (wallet adress)}",

   "all credentials" : "http://localhost:3007/workers/{user_id (wallet adress)}",
   "workers rating" :" http://localhost:3007/worker-rating/{platform key}/{user_id (wallet adress)}",
   "ratings above limit" : "http://localhost:3007/all-ratings-above/{platform key}/{rating}"
   }
}
``` 

## Architecture

The conceptual architecture of the various components

![architecture](human-credentialing.pptx)


