<script>
    import Navigation from "$lib/components/Navigation.svelte";
    import ContactSection from "$lib/components/ContactSection.svelte";

    import global from '../global.css'
</script>

<Navigation />

<slot />

<ContactSection />