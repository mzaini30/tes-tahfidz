<div class="container">
	<br>
	<h3 class="text-center">Tes Tahfidz</h3>
	<hr>
	<div class="row">
		<div class="col">
			<div class="form-group">
				<label>Hari Ujian <br><small>(Isi antara 1 sampai 5)</small></label>
				<div class="input-group">
					<div class="input-group-prepend">
						<span class="input-group-text">Ke</span>
					</div>
					<input type="tel" class="form-control" bind:value={hariUjian} name="">
				</div>
			</div>
		</div>
		<div class="col">
			<div class="form-group">
				<label>Juz yang Diujikan <br><small>(Isi antara 1 sampai 30)</small></label>
				<div class="input-group">
					<input type="tel" class="form-control" bind:value={juz} name="">
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
			<button class="btn btn-success" on:click={cariAyat}>Mulai</button>
		</div>
	</div>
</div>
<script type="text/javascript">
	import {acak} from '@/tools/acak'
	let hariUjian = ''
	let juz = ''
	let juz30 = []
	let listHalaman = []
	for (let x = 572; x <= 604; x++){
		juz30 = [...juz30, x]
	}
	function cariAyat(){
		listHalaman = []
		if (juz == 1) {
			listHalaman = [...juz30]
		} else {
			let halamanTertinggi = (juz - 1) * 20 + 1
			for (let x = 1; x <= halamanTertinggi; x++){
				listHalaman = [...listHalaman, x]
			}
			listHalaman = [...juz30, ...listHalaman]
		}
		let ambil = ''
		let dataBaru = []
		let minimal = Math.round(listHalaman.length * (hariUjian - 1) / 5)
		let maksimal = Math.round(listHalaman.length * hariUjian / 5)
		for (let n = minimal; n < maksimal; n++){
			dataBaru = [...dataBaru, listHalaman[n]]
		}
		ambil = acak(dataBaru)[0]
		Swal.fire(`Halaman ${ambil}`)
	}
</script>
