<script>

	import Header from "./UI/Header.svelte";
    import MeetupGrid from "./MeetUps/MeetupGrid.svelte";
	import TextInput from "./UI/TextInput.svelte";
	import Button from "./UI/Button.svelte";

	let title = '';
	let subtitle = '';
	let address = '';
	let imageURL = '';
	let email = '';
	let description = '';


	let meetups = [
		{
			id: 'm1',
			title: 'Coding Bootcamp',
			subtitle: 'Learn code fast',
			description: 'In this meetup we will practice code',
			imageURL: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?fm=jpg&q=60&w=3000&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8Y29kaW5nfGVufDB8fDB8fHww",
			address: "27 Joy St.",
			contactEmail: 'code@test.com',
		},
		{
			id: 'm2',
			title: 'Swimming Camp',
			subtitle: 'Enjoy swimming with your friends from all over',
			description: 'Swimming classes, freetime and more!',
			imageURL: "https://clearcomfort.com/wp-content/uploads/2019/05/AdobeStock_34148619-1024x683.jpeg",
			address: "21 Jump Street",
			contactEmail: 'swim@justdive.com',
		}
	]

	function addMeetUp () {
		const newMeetup = {
			id: Math.random().toString(),
			title: title,
			subtitle: subtitle,
			description: description,
			imageURL: imageURL,
			address: address,
			contactEmail: email,
		};

		meetups = [...meetups, newMeetup];
	}
</script>

<style>
	main {
		margin-top: 5rem;
	}

	form {
		width: 30rem;
		max-width: 90%;
		margin: auto;
	}
</style>

<Header />
<!-- The on:input event handler is initiated when user activates input. It takes the event of input, and grabs the value 
 setting it equal to title-->
<main>
	<form on:submit|preventDefault="{addMeetUp}">
		<TextInput 
			id="title" 
			label="Title" 
			value={title} 
			on:input = { event => ( title = event.target.value) }
			type="text"
		/>
		<TextInput 
			id="subtitle" 
			label="Subtitle" 
			value={subtitle} 
			on:input = { event => ( subtitle = event.target.value) }
			type="text"
		/>
		<TextInput 
			id="address" 
			label="Address" 
			value={address} 
			on:input = { event => ( address = event.target.value) }
			type="text"
		/>
		<TextInput 
			id="imageURL" 
			label="ImageURL" 
			value={imageURL} 
			on:input = { event => ( imageURL = event.target.value) }
			type="text"
		/>
		<TextInput 
			id="email" 
			label="E-mail" 
			value={email} 
			on:input = { event => ( email = event.target.value) }
			type="email"
		/>
		<TextInput 
			id="descrption" 
			label="Description" 
			value={description} 
			on:input = { event => ( description = event.target.value) }
			controlType="textarea"
			rows=3
		/>
		<Button type="submit" caption="Save"/>
	</form>
	<MeetupGrid {meetups}/>
</main>