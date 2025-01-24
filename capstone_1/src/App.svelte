<script>

	import Header from "./UI/Header.svelte";
	import MeetupItem from "./MeetUps/MeetupItem.svelte";
	const meetups = [
		{
			id: 'm1',
			title: 'Coding Bootcamp',
			subtitle: 'Learn code fast',
			description: 'In his meetup we will practice code',
			imgURL: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?fm=jpg&q=60&w=3000&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8Y29kaW5nfGVufDB8fDB8fHww",
			address: "27 Joy St.",
			contactEmail: 'code@test.com',
		},
		{
			id: 'm2',
			title: 'Swimming Camp',
			subtitle: 'Enjoy swimming with your friends from all over',
			description: 'Swimming classes, freetime and more!',
			imgURL: "https://clearcomfort.com/wp-content/uploads/2019/05/AdobeStock_34148619-1024x683.jpeg",
			contactEmail: 'swim@justdive.com',
		}
	]
</script>

<Header />

{#each meetups as meetup}
	<MeetupItem />
{/each}

