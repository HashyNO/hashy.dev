<script setup lang="ts">
	const API_URL = `https://api.github.com/users/hashyno/repos`
	const { data: repos } = await useFetch(API_URL)

	function formatDate(v: string) {
		return v.split("T")[0]
	}
</script>


<template>
	<h1>My repos</h1>
	<ul>
		<li v-for="{ html_url, full_name, description, created_at, updated_at } in repos" :key="html_url">
			<a :href="html_url" target="_blank" class="name"><b>{{full_name}}</b></a>
			<span class="Description">
				<p target="_blank">{{ description }}</p>
			</span>
			Created: <span class="CreatedAt">
				{{ formatDate(created_at) }}
			</span>
			Updated: <span class="UpdatedAt">
				{{ formatDate(updated_at) }}
			</span>
		</li>
	</ul>
</template>
