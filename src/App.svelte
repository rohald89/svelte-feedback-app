<script>
  import FeedbackList from "./components/Feedbacklist.svelte";

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

  const deleteFeedback = (e) => {
    const itemId = e.detail;

    feedback = feedback.filter((item) => item.id !== itemId);
  };
</script>

<main class="container">
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
