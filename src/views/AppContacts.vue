<script>
export default {
    name: 'AppContacts'
}
</script>

<template>
    <!-- Contact me -->
    <div class="contact-us">
        <h1>Contact Me</h1>

        <!-- Contact me form -->
        <form action="#">

            <!-- Name input -->
            <label for="customerName">NAME <em>&#x2a;</em></label>
            <input id="customerName" name="customerName" required="" type="text" />

            <!-- Email input -->
            <label for="customerEmail">EMAIL
                <em>&#x2a;</em>
            </label>
            <input id="customerEmail" name="customerEmail" required="" type="email" />

            <!-- Phone input -->
            <label for="customerPhone">PHONE</label>
            <input id="customerPhone" name="customerPhone" type="tel" />

            <!-- Message input -->
            <label for="customerNote">YOUR MESSAGE
                <em>&#x2a;</em></label>
            <textarea id="customerNote" name="customerNote" required="" rows="4"></textarea>

            <!-- Submit form button -->
            <button id="customerOrder">SUBMIT</button>

        </form>
    </div>
</template>



<style lang="scss" scoped></style>