<script>
	import storeData from './store/store.js'
	import BtnToggleMode from './BtnToggleMode.svelte'
	let data;

	storeData.subscribe(valeur => {
		data = valeur;
	});


</script>


<div class={data ? "conteneur go-light" : "conteneur go-dark"}>
	<BtnToggleMode />
	<h1>Lorem ipsum dolor sit amet.</h1>
	<p class="contenu">
		Lorem ipsum dolor sit, amet consectetur adipisicing elit. Modi facere accusamus at assumenda omnis provident deserunt repellendus maiores esse blanditiis, praesentium neque quam voluptatibus, vitae, tenetur voluptate iste fugiat architecto sequi. Voluptatem pariatur neque porro rem alias vitae quos asperiores commodi beatae maxime veniam harum, iste temporibus velit omnis voluptatum libero, tenetur fuga delectus sequi? Cupiditate impedit in id, culpa magni animi aliquam? Adipisci quaerat nesciunt labore, autem doloribus nam. Iste, quasi illo sed ipsam nostrum pariatur id, quisquam explicabo rerum voluptas quo. Expedita quisquam sint modi facilis! Laudantium nemo reiciendis reprehenderit rem ducimus eum aspernatur dolores optio fugiat provident saepe dicta itaque quo, non consequatur voluptatem nostrum at facilis! Odit vero, fuga quae non illum quos inventore facilis consequuntur minus nesciunt culpa et obcaecati quis minima eum libero voluptatem nulla cumque qui? Minus non tempore sapiente voluptatibus dolorum eveniet natus ratione quam accusantium iste nostrum necessitatibus obcaecati, fuga voluptas perferendis itaque aut officia nulla temporibus debitis. Incidunt soluta eligendi nulla saepe velit tempore? Repudiandae saepe veritatis aperiam iure iusto nulla suscipit autem, dignissimos necessitatibus vitae delectus quod a dolores temporibus vero mollitia esse ad totam ratione, blanditiis, molestias consectetur qui dolore. Ipsa sed dicta, vero blanditiis minus, porro inventore a harum sint in quo iste velit laborum doloribus ex suscipit voluptatibus illo laboriosam. Corrupti eaque eveniet qui aspernatur dignissimos. Explicabo autem cupiditate eos ipsum harum molestias nihil odio? Nesciunt at doloribus debitis quia voluptates hic itaque animi possimus, quos error. Id ratione eos, similique corporis obcaecati, magnam, molestiae officia totam natus excepturi amet aperiam numquam blanditiis nemo? Repellat blanditiis delectus rerum possimus. Facilis pariatur laudantium quos sit eligendi quaerat voluptates dolores, tempore doloremque placeat magnam modi consectetur a voluptate, magni, aspernatur ab dolorum nesciunt? Similique eius, provident commodi reprehenderit saepe neque deserunt autem omnis labore aliquam dolorem, esse fuga dolores laudantium distinctio impedit iure necessitatibus! Quis, soluta cumque! Ea, quia. Eum corrupti molestias vel dolores alias ut ipsa doloremque et doloribus, illo, in, nulla obcaecati debitis perferendis! Odio doloribus officiis perspiciatis, maxime nulla debitis soluta pariatur ex quaerat, laudantium iste laborum ad nesciunt asperiores voluptatibus. Animi natus accusamus, quaerat corrupti numquam illum reprehenderit dignissimos eaque voluptas optio sint obcaecati, a, officia est quidem. Praesentium minima odit quis tempora. Accusamus, illum! Nulla corrupti exercitationem dolorum vel laborum nesciunt facilis, perferendis, laudantium, quibusdam tenetur ipsam accusamus ut sint earum labore nihil! Cumque modi odio fugit dignissimos velit? Atque, consectetur reprehenderit? Eos accusantium iure veritatis sint. Perferendis animi eaque veritatis odit laboriosam, voluptate corporis aut voluptatem vel rerum quidem cumque commodi natus harum ratione minima provident modi, beatae explicabo labore corrupti! Maiores quos atque id temporibus reprehenderit! Nam facere adipisci sit architecto error dicta doloribus fuga odit debitis officia est distinctio, molestias iure excepturi temporibus fugit deserunt expedita at non enim, amet mollitia ea libero. Facilis perferendis porro libero consectetur. Suscipit consequatur assumenda, error perferendis, corrupti necessitatibus exercitationem, deserunt laboriosam ullam saepe amet recusandae animi quia voluptates iusto. Ipsam repudiandae saepe accusamus deleniti! Quam omnis molestias, quaerat dolorum aperiam in modi et?
	</p>

</div>


<style>

	h1 {
		text-align: center;
		padding: 25px 80px;
	}
	.conteneur {
		width: 100%;
		height: auto;
		min-height: 100vh;
		transition: color 0.2s ease-in, background-color 0.2s ease-in;
	}
	.contenu {
		padding: 10px 5vw;
	}
</style>

