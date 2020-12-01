<div class="container">
	<br>
	<h3 class="text-center">Tes Tahfidz</h3>
	<hr>
	<div class="row">
		<div class="col">
			<div class="form-group">
				<label>Hari Ujian</label>
				<div class="input-group">
					<div class="input-group-prepend">
						<span class="input-group-text">Ke</span>
					</div>
					<input type="tel" class="form-control" bind:value={hariUjian} placeholder="1" name="">
				</div>
			</div>
		</div>
		<div class="col">
			<div class="form-group">
				<label>Juz yang Diujikan</label>
				<div class="input-group">
					<input type="tel" class="form-control" bind:value={juz} placeholder="5" name="">
					<div class="input-group-append">
						<span class="input-group-text">Juz</span>
					</div>
				</div>
			</div>
		</div>
	</div>
	<div class="d-flex justify-content-between">
		<div>
			<button class="btn btn-warning" on:click={() => juz = ''}>Reset</button>
		</div>
		<div>
			<button class="btn btn-success">Mulai</button>
		</div>
	</div>
</div>
<script type="text/javascript">
	let hariUjian = ''
	let juz = ''
</script>