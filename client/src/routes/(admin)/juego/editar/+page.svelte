<script lang="ts">
  import type { Game, GameQuestion } from '../../../../@types/game'
  import ActualQuestionEdit from './components/ActualQuestionEdit.svelte'

  import Error from './components/Error.svelte'
  import Questions from './components/Questions.svelte'

  export let data: Game
  const game = data

  let gameQuestions: GameQuestion[] = []
  let keyActualQuestionEdit: number = 0

  if (game && game.gameQuestions !== null) {
    gameQuestions = game.gameQuestions
  } else {
    gameQuestions = []
  }

  let editSuccess: boolean = true
</script>

<svelte:head>
  <title>Editar {game?.gameId} Game</title>
</svelte:head>

<Error {editSuccess} />
<div class="container mx-auto">
  <div class="mt-4 flex flex-row">
    <div class="basis-2/6">
      <Questions
        {game}
        bind:editSuccess
        bind:gameQuestions
        bind:keyActualQuestionEdit
      />
    </div>
    <div class="basis-4/6">
      <ActualQuestionEdit bind:keyActualQuestionEdit bind:gameQuestions />
    </div>
  </div>
</div>
