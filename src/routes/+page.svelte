<script lang="ts">
	// The Resume link appears automatically once static/resume.pdf exists.
	const hasResume = Object.keys(import.meta.glob('/static/resume.pdf')).length > 0;

	const links = [
		...(hasResume ? [{ label: 'Resume', href: '/resume.pdf' }] : []),
		{ label: 'Email', href: 'mailto:wolmstead@ucsd.edu' },
		{ label: 'GitHub', href: 'https://github.com/olmsteadv5' },
		{ label: 'LinkedIn', href: 'https://www.linkedin.com/in/william-olmstead-83a4792b7/' },
		{ label: 'Robolyst', href: 'https://robolyst.org/team-management' }
	];
</script>

<svelte:head>
	<title>William Olmstead</title>
	<meta name="description" content="William Olmstead — resume, contact, GitHub, and LinkedIn." />
</svelte:head>

<main
	class="flex min-h-svh flex-col items-center justify-center bg-white px-4 text-neutral-900 dark:bg-neutral-950 dark:text-neutral-100"
>
	<h1 class="text-4xl font-semibold tracking-tight sm:text-5xl">William Olmstead</h1>

	<nav class="mt-8 flex flex-wrap justify-center gap-x-6 gap-y-3 text-lg">
		{#each links as link (link.label)}
			<a
				href={link.href}
				class="underline decoration-neutral-300 underline-offset-4 transition-colors hover:decoration-current dark:decoration-neutral-700"
				target={link.href.startsWith('http') ? '_blank' : undefined}
				rel={link.href.startsWith('http') ? 'noopener noreferrer' : undefined}>{link.label}</a
			>
		{/each}
	</nav>

	<footer class="absolute bottom-6 text-sm text-neutral-500">Improved website coming soon</footer>
</main>
