<script>
  import FeedbackForm from "./components/FeedbackForm.svelte";
  import FeedbackList from "./components/Feedbacklist.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";
  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat nisi, ipsa dolor dicta iure unde consequatur excepturi aliquam quos. Recusandae quam consectetur officiis modi similique rerum reprehenderit fugiat laboriosam est.",
    },
    {
      id: 2,
      rating: 9,
      text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat nisi, ipsa dolor dicta iure unde consequatur excepturi aliquam quos. Recusandae quam consectetur officiis modi similique rerum reprehenderit fugiat laboriosam est.",
    },
    {
      id: 3,
      rating: 8,
      text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat nisi, ipsa dolor dicta iure unde consequatur excepturi aliquam quos. Recusandae quam consectetur officiis modi similique rerum reprehenderit fugiat laboriosam est.",
    },
  ];

  $: count = feedback.length;
  $: average =
    feedback.reduce((acc, curr) => acc + curr.rating, 0) / feedback.length;

  const deleteFeedback = (e) => {
    const itemId = e.detail;

    feedback = feedback.filter((item) => item.id !== itemId);
  };

  const addFeedback = (e) => {
    const newFeedback = e.detail;

    feedback = [...feedback, newFeedback];
  };
</script>

<main class="container">
  <FeedbackForm on:add-feedback={addFeedback} />
  <FeedbackStats {count} {average} />
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
