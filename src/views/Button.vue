<template>
    <h1 class="heading-1">Button</h1>
    <h2 class="heading-2">Disabled</h2>
    <div class="line">
        <Button label="primary" color="primary" :disabled="true"/>
        <Button label="Secondary" color="second" :disabled="true"/>
    </div>
    <h2 class="heading-2">Colors</h2>
    <div class="line">
        <Button label="primary" color="primary"/>
        <Button label="Secondary" color="second"/>
        <Button label="Success" color="success"/>
        <Button label="Info" color="info"/>
        <Button label="Warning" color="warning"/>
        <Button label="Danger" color="danger"/>
    </div>
    <h2 class="heading-2">Rounded</h2>
    <div class="line">
        <Button label="primary" color="primary" rounded/>
        <Button label="Secondary" color="second" rounded/>
        <Button label="Success" color="success" rounded/>
        <Button label="Info" color="info" rounded/>
        <Button label="Warning" color="warning" rounded/>
        <Button label="Danger" color="danger" :rounded="true"/>
    </div>
    <h2 class="heading-2">Outlined</h2>
    <div class="line">
        <Button label="primary" color="primary" outlined/>
        <Button label="Secondary" color="second" outlined/>
        <Button label="Success" color="success" outlined/>
        <Button label="Info" color="info" outlined/>
        <Button label="Warning" color="warning" outlined/>
        <Button label="Danger" color="danger" :outlined="true"/>
    </div>
    <h2 class="heading-2">Icon</h2>
    <div class="line">
        <Button color="primary" icon="heart" outlined/>
        <Button color="second" icon="hand"/>
        <Button color="success" icon="address-book" outlined/>
        <Button color="info" icon="credit-card"/>
        <Button color="warning" icon="lemon" outlined/>
        <Button color="danger" icon="hourglass"/>
    </div>
    <h2 class="heading-2">Outlined</h2>
    <div class="line">
        <Button label="Large" color="primary" size="large"/>
        <Button label="Normal" color="second" />
    </div>
    <h2 class="heading-2">Event</h2>
    <div class="line">
        <Button label="@click" color="danger" @test="eventForButton"/>

    </div>
</template>

<script setup>
import Button from '@/components/Button.vue'

const eventForButton = () => {
    alert("click")
}
</script>

<style lang="scss" scoped>

</style>