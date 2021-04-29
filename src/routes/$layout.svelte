<script context="module">
	export async function load({ page }) {
		const { app, metric, appId, ping, table } = page.params;

		const links = [
			...(app
				? [
						{ url: '/', name: 'apps' },
						{ url: `/${app}/`, name: app }
				  ]
				: []),
			...(appId ? [{ url: `/${app}/app_ids/${appId}/`, name: appId }] : []),
			...(ping ? [{ url: `/${app}/pings/${ping}/`, name: ping }] : []),
			...(metric
				? [
						{
							url: `/${app}/metrics/${metric}/`,
							name: metric
						}
				  ]
				: []),
			...(table
				? [
						{
							url: `/${app}/app_ids/${appId}/tables/${table}/`,
							name: table
						}
				  ]
				: [])
		];

		return { props: { links } };
	}
</script>

<script>
	export let links;
	import Header from '$lib/Header.svelte';
	import Footer from '$lib/Footer.svelte';
	import BreadCrumb from '$lib/BreadCrumb.svelte';
	import '../main.scss';
</script>

<Header />

<main>
	<BreadCrumb {links} />
	<slot />
</main>

<Footer />
