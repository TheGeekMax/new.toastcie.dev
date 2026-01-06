<script lang="ts">
	import { onMount } from 'svelte';
	import { fly, fade } from 'svelte/transition';
	
	let currentRoleIndex = 0;
	let roles = ['Developpeur', 'Game Designer', 'Ingénieur', 'Tuteur', 'DevOps Enthusiast', 'Tech Lover', 'Unity User'];
	
	onMount(() => {
		const interval = setInterval(() => {
			currentRoleIndex = (currentRoleIndex + 1) % roles.length;
		}, 2000);
		
		return () => clearInterval(interval);
	});
</script>

<div class="home-container">
	<div class="left-content">
		<h1 class="brand">TOASTCIE</h1>
		<div class="role-container">
			{#key currentRoleIndex}
				<span 
					class="role"
					in:fly={{ y: 20, duration: 600, delay: 100 }}
					out:fly={{ y: -20, duration: 400 }}
				>
					{roles[currentRoleIndex]}
				</span>
			{/key}
		</div>
	</div>
	
	<div class="rocket-section">
		<div class="rocket-wrapper">
			<img src="/img/space.svg" alt="Rocket" class="rocket" />
		</div>
		<div class="connector-line"></div>
	</div>
	
	<div class="right-content">
		<p class="description">
			Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptates, autem quod inventore ea saepe nemo cupiditate libero, molestias nihil sed nulla excepturi impedit amet molestiae sapiente temporibus et veritatis placeat?
		</p>
	</div>
</div>

<style>
	.home-container {
		display: flex;
		align-items: flex-start;
		gap: 4rem;
		max-width: 1400px;
		padding: 2rem;
		justify-content: center;
	}
	
	/* Rocket Section */
	.rocket-section {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	
	.rocket-wrapper {
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
		z-index: 2;
	}
	
	.rocket {
		width: 120px;
		height: auto;
	}
	
	/* Connector Line */
	.connector-line {
		position: relative;
		width: 35px;
		height: 300px;
		z-index: 1;
		background: linear-gradient(
			to bottom,
			rgba(150, 200, 255, 0.95) 0%,
			rgba(120, 180, 255, 0.9) 10%,
			rgba(100, 160, 255, 0.85) 20%,
			rgba(80, 140, 255, 0.75) 35%,
			rgba(60, 120, 240, 0.6) 50%,
			rgba(40, 100, 220, 0.45) 65%,
			rgba(30, 80, 200, 0.3) 80%,
			rgba(20, 60, 180, 0.15) 90%,
			rgba(10, 40, 160, 0) 100%
		);
		clip-path: polygon(
			25% 0%, 75% 0%,
			68% 15%,
			63% 35%,
			60% 55%,
			57% 75%,
			65% 100%,
			35% 100%,
			43% 75%,
			40% 55%,
			37% 35%,
			32% 15%
		);
		margin-top: -5px;
		filter: blur(1.5px);
		box-shadow: 
			0 0 20px rgba(120, 180, 255, 0.8),
			0 0 40px rgba(80, 140, 255, 0.6),
			0 0 60px rgba(100, 160, 255, 0.4);
	}
	
	/* Content Sections */
	.left-content {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		justify-content: center;
		margin-top: 150px;
	}
	
	.right-content {
		display: flex;
		align-items: center;
		justify-content: center;
        max-width: 400px;
		margin-top: 150px;
    }

	/* Text Styles */
	.brand {
		font-size: 4rem;
		font-weight: 700;
		color: #ffffff;
		margin: 0;
		letter-spacing: 0;
		line-height: 1;
	}
	
	.role-container {
		height: 2.5rem;
		overflow: hidden;
		margin-top: 0.5rem;
		position: relative;
		min-width: 200px;
	}
	
	.role {
		display: block;
		font-size: 1.3rem;
		color: #c4c0d0;
		font-weight: 300;
		letter-spacing: 0;
		white-space: nowrap;
		position: absolute;
		left: 0;
		top: 0;
		width: 100%;
	}
	
	.description {
		color: #ffffff;
		font-size: 1.2rem;
		font-weight: 400;
		margin: 0;
		max-width: 300px;
		line-height: 1.6;
	}
	
	/* Animations */
	@keyframes slideInUp {
		from {
			opacity: 0;
			transform: translateY(30px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
	
	@keyframes fadeIn {
		from {
			opacity: 0;
			transform: translateY(-10px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
	
	/* Responsive Design */
	@media (max-width: 768px) {
		.content-section {
			flex-direction: column;
			gap: 2rem;
			align-items: center;
		}
		
		.home-container {
			flex-direction: column;
			gap: 2rem;
			align-items: center;
		}
		
		.left-content {
			align-items: center;
			order: 2;
		}
		
		.rocket-section {
			order: 1;
		}
		
		.right-content {
			order: 3;
        }

		.role {
			font-size: 1.2rem;
		}
		
		.description {
			font-size: 1.5rem;
			text-align: center;
		}
		
		.connector-line {
			height: 100px;
		}
	}
</style>
