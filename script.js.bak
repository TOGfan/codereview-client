new Vue({
    el: '#app',
    data: {
      userName: '',
      user: null
    },
    methods: {
      async saveUser() {
        try {
          const response = await fetch('http://localhost:8080/api/v1/user/', {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json'
            },
            body: JSON.stringify({ 
                email: this.userName,
                password: "12345678",
                username: this.userName
            })
          });
          const data = await response.json();
          console.log(data); // Log the response from the server
          alert('User saved successfully!');
          alert(JSON.stringify({ 
            email: this.userName,
            password: "12345678",
            username: this.userName
        }));
        } catch (error) {
          console.error('Error saving user:', error);
          alert('An error occurred while saving user.');
        }
      },
      async getUser() {
        try {
          const response = await fetch('http://localhost:8080/api/v1/user/');
          const data = await response.json();
          alert(data["data"]);
          if (data["data"].length > 0) {
            this.user = data["data"][0]; // Assuming you want to retrieve the first user
          } else {
            alert('No user found.');
          }
        } catch (error) {
          console.error('Error getting user:', error);
          alert('An error occurred while getting user.');
        }
      }
    }
  });