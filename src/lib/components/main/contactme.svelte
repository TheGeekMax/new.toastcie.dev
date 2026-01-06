<script lang="ts">
	import { Mail, Github, Linkedin, Send, Briefcase } from '@lucide/svelte';
</script>

<div class="contact-container">
	<div class="left-content">
		<div class="section-header">
			<Mail size={48} class="header-icon" />
			<h2 class="section-title">Contact</h2>
		</div>
		<div class="contact-form">
			<form>
				<div class="form-group">
					<label for="name">Nom</label>
					<input type="text" id="name" name="name" placeholder="Votre nom" />
				</div>
				
				<div class="form-group">
					<label for="email">Email</label>
					<input type="email" id="email" name="email" placeholder="votre@email.com" />
				</div>
				
				<div class="form-group">
					<label for="message">Message</label>
					<textarea id="message" name="message" rows="5" placeholder="Votre message..."></textarea>
				</div>
				
				<button type="submit" class="submit-btn">
					<Send size={18} />
					<span>Envoyer</span>
				</button>
			</form>
		</div>
	</div>
	
	<div class="center-divider">
		<div class="vertical-line"></div>
	</div>
	
	<div class="right-content">
		<div class="contact-grid">
			<a href="mailto:maxime@toastcie.dev" class="contact-card">
				<Mail size={40} />
				<span>Email</span>
			</a>
			
			<a href="https://linkedin.com/in/maxime-sanciaume" target="_blank" rel="noopener noreferrer" class="contact-card">
				<Linkedin size={40} />
				<span>LinkedIn</span>
			</a>
			
			<a href="https://github.com/thegeekmax" target="_blank" rel="noopener noreferrer" class="contact-card">
				<Github size={40} />
				<span>GitHub</span>
			</a>
			
			<a href="https://www.malt.fr/profile/maximesanciaume" target="_blank" rel="noopener noreferrer" class="contact-card">
				<Briefcase size={40} />
				<span>Malt</span>
			</a>
		</div>
	</div>
</div>

<style>
	.contact-container {
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
		max-width: 550px;
        min-width: 400px;
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
		text-align: justify;
	}
	
	/* Contact Form */
	.contact-form {
		width: 100%;
		margin-top: 1rem;
	}
	
	.contact-form form {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}
	
	.form-group {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}
	
	.form-group label {
		color: #b4d9ff;
		font-size: 1rem;
		font-weight: 600;
		letter-spacing: 0.5px;
	}
	
	.form-group input,
	.form-group textarea {
		background: rgba(255, 255, 255, 0.06);
		border: 1px solid rgba(255, 255, 255, 0.15);
		border-radius: 8px;
		padding: 0.875rem 1rem;
		color: #ffffff;
		font-size: 1rem;
		font-family: inherit;
		transition: all 0.3s ease;
		resize: vertical;
	}
	
	.form-group input::placeholder,
	.form-group textarea::placeholder {
		color: rgba(196, 192, 208, 1);
	}
	
	.form-group input:focus,
	.form-group textarea:focus {
		outline: none;
		border-color: rgba(150, 200, 255, 0.5);
		background: rgba(255, 255, 255, 0.05);
		box-shadow: 0 0 15px rgba(120, 180, 255, 0.2);
	}
	
	.submit-btn {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 0.5rem;
		background: rgba(150, 200, 255, 0.15);
		border: 1px solid rgba(150, 200, 255, 0.4);
		border-radius: 8px;
		padding: 0.875rem 1.5rem;
		color: #b4d9ff;
		font-size: 1rem;
		font-weight: 600;
		cursor: pointer;
		transition: all 0.3s ease;
		margin-top: 0.5rem;
	}
	
	.submit-btn:hover {
		background: rgba(150, 200, 255, 0.2);
		border-color: rgba(150, 200, 255, 0.5);
		box-shadow: 0 0 20px rgba(120, 180, 255, 0.3);
		transform: translateY(-2px);
	}
	
	.submit-btn:active {
		transform: translateY(0);
	}
	
	/* Center Divider */
	.center-divider {
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 50px;
	}
	
	.vertical-line {
        margin-top:150px;
		width: 3px;
		height: 200px;
		background: rgba(150, 200, 255, 0.8) 0%;
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
	
	.contact-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 1.5rem;
		width: 100%;
	}
	
	.contact-card {
		aspect-ratio: 1;
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.1);
		border-radius: 12px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 0.75rem;
		transition: all 0.3s ease;
		backdrop-filter: blur(10px);
		text-decoration: none;
		color: #96c8ff;
		padding: 1rem;
	}
	
	.contact-card:hover {
		background: rgba(255, 255, 255, 0.05);
		border-color: rgba(150, 200, 255, 0.3);
		transform: translateY(-5px);
		box-shadow: 
			0 0 20px rgba(120, 180, 255, 0.2),
			0 5px 15px rgba(0, 0, 0, 0.3);
		color: #b4d9ff;
	}
	
	.contact-card span {
		font-size: 1rem;
		font-weight: 500;
		color: #ffffff;
		text-align: center;
	}
	
	/* Header Icon */
	:global(.header-icon) {
		color: #96c8ff;
		filter: drop-shadow(0 0 10px rgba(150, 200, 255, 0.5));
	}
	
	/* Responsive Design */
	@media (max-width: 768px) {
		.contact-container {
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
		
		.contact-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}
	
	@media (max-width: 480px) {
		.section-title {
			font-size: 2rem;
		}
		
		.contact-grid {
			grid-template-columns: 1fr;
		}
	}
</style>
