<script lang="ts">
	import { fly, fade } from 'svelte/transition';
	import { User, Code2, Lightbulb, Heart } from '@lucide/svelte';
</script>

<div class="about-container">
	<div class="left-content">
		<div class="section-header">
			<User size={48} class="header-icon" />
			<h2 class="section-title">À Propos</h2>
		</div>
		<div class="intro-text">
			<p class="main-description">
				Passionné par la technologie et l'innovation, je suis un développeur qui aime créer 
				des expériences numériques uniques et engageantes.
			</p>
		</div>
	</div>
	
	<div class="center-divider">
		<div class="vertical-line"></div>
	</div>
	
	<div class="right-content">
		<div class="info-cards">
			<div class="info-card">
				<div class="card-icon">
					<Code2 size={32} />
				</div>
				<h3 class="card-title">Développement</h3>
				<p class="card-description">
					Créateur d'applications web et de jeux, avec une expertise en développement full-stack 
					et une passion pour les nouvelles technologies.
				</p>
			</div>
			
			<div class="info-card">
				<div class="card-icon">
					<Lightbulb size={32} />
				</div>
				<h3 class="card-title">Innovation</h3>
				<p class="card-description">
					Toujours à la recherche de solutions créatives et efficaces pour résoudre 
					des problèmes complexes.
				</p>
			</div>
			
			<div class="info-card">
				<div class="card-icon">
					<Heart size={32} />
				</div>
				<h3 class="card-title">Passion</h3>
				<p class="card-description">
					Engagé dans le partage de connaissances en tant que tuteur, 
					j'aime aider les autres à progresser dans le monde du développement.
				</p>
			</div>
		</div>
	</div>
</div>

<style>
	.about-container {
		display: flex;
		align-items: flex-start;
		gap: 4rem;
		max-width: 1400px;
		padding: 2rem;
		justify-content: center;
	}
	
	/* Left Content */
	.left-content {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		justify-content: flex-start;
		max-width: 400px;
		margin-top: 50px;
	}
	
	.section-header {
		display: flex;
		align-items: center;
		gap: 1rem;
		margin-bottom: 2rem;
	}
	
	.section-title {
		font-size: 3rem;
		font-weight: 700;
		color: #ffffff;
		margin: 0;
		letter-spacing: 0;
	}
	
	.intro-text {
		margin-top: 1rem;
	}
	
	.main-description {
		color: #c4c0d0;
		font-size: 1.2rem;
		font-weight: 300;
		line-height: 1.8;
		margin: 0;
	}
	
	/* Center Divider */
	.center-divider {
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 50px;
	}
	
	.vertical-line {
		width: 3px;
		height: 400px;
		background: linear-gradient(
			to bottom,
			rgba(150, 200, 255, 0.8) 0%,
			rgba(100, 160, 255, 0.6) 50%,
			rgba(60, 120, 240, 0.3) 100%
		);
		box-shadow: 
			0 0 15px rgba(120, 180, 255, 0.5),
			0 0 25px rgba(80, 140, 255, 0.3);
		border-radius: 2px;
	}
	
	/* Right Content */
	.right-content {
		display: flex;
		align-items: flex-start;
		justify-content: center;
		max-width: 500px;
		margin-top: 50px;
	}
	
	.info-cards {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
		width: 100%;
	}
	
	.info-card {
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.1);
		border-radius: 12px;
		padding: 1.5rem;
		transition: all 0.3s ease;
		backdrop-filter: blur(10px);
		transform: translateX(0);
	}
	
	.info-card:hover {
		background: rgba(255, 255, 255, 0.05);
		border-color: rgba(150, 200, 255, 0.3);
		transform: translateX(5px);
		box-shadow: 
			0 0 20px rgba(120, 180, 255, 0.2),
			0 5px 15px rgba(0, 0, 0, 0.3);
	}
	
	.card-icon {
		color: #96c8ff;
		margin-bottom: 1rem;
		display: flex;
		align-items: center;
	}
	
	.card-title {
		font-size: 1.5rem;
		font-weight: 600;
		color: #ffffff;
		margin: 0 0 0.75rem 0;
		letter-spacing: 0;
	}
	
	.card-description {
		color: #c4c0d0;
		font-size: 1rem;
		font-weight: 300;
		line-height: 1.6;
		margin: 0;
	}
	
	/* Header Icon */
	:global(.header-icon) {
		color: #96c8ff;
		filter: drop-shadow(0 0 10px rgba(150, 200, 255, 0.5));
	}
	
	/* Responsive Design */
	@media (max-width: 768px) {
		.about-container {
			flex-direction: column;
			gap: 2rem;
			align-items: center;
		}
		
		.left-content {
			align-items: center;
			text-align: center;
			margin-top: 20px;
		}
		
		.section-header {
			flex-direction: column;
			gap: 0.5rem;
		}
		
		.center-divider {
			margin-top: 20px;
		}
		
		.vertical-line {
			width: 80%;
			height: 3px;
			background: linear-gradient(
				to right,
				rgba(150, 200, 255, 0.8) 0%,
				rgba(100, 160, 255, 0.6) 50%,
				rgba(60, 120, 240, 0.3) 100%
			);
		}
		
		.right-content {
			margin-top: 20px;
		}
		
		.section-title {
			font-size: 2.5rem;
		}
		
		.main-description {
			font-size: 1.1rem;
		}
		
		.info-card:hover {
			transform: translateY(-5px);
		}
	}
	
	@media (max-width: 480px) {
		.section-title {
			font-size: 2rem;
		}
		
		.card-title {
			font-size: 1.3rem;
		}
		
		.card-description {
			font-size: 0.95rem;
		}
	}
</style>
