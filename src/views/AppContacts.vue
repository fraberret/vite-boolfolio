<script>
export default {
    name: 'AppContacts'
}
</script>

<template>
    <div class="contact-us">
        <h1>Contact Me</h1>
        <form action="#">
            <label for="customerName">NAME <em>&#x2a;</em></label>
            <input id="customerName" name="customerName" required="" type="text" /><label for="customerEmail">EMAIL
                <em>&#x2a;</em>
            </label>
            <input id="customerEmail" name="customerEmail" required="" type="email" />
            <label for="customerPhone">PHONE</label>

            <input id="orderNumber" name="orderNumber" type="text" />
            <label for="customerNote">YOUR MESSAGE
                <em>&#x2a;</em></label>

            <textarea id="customerNote" name="customerNote" required="" rows="4"></textarea>
            <button id="customerOrder">SUBMIT</button>
        </form>
    </div>
</template>



<style lang="scss" scoped></style>