<template>
    <div class="bd-example">
      <form>

          <h1>Bot Setup</h1>
          <div class="mb-3">
              <label for="exampleInputEmail1" class="form-label">姓名</label>
              <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
          </div>
          <div class="mb-3">
              <label for="exampleInputPassword1" class="form-label">性格</label>
              <input type="password" class="form-control" id="exampleInputPassword1">
          </div>

          <div class="mb-3">
              <label for="exampleFormControlTextarea1" class="form-label">生平经历/背景设定</label>
              <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
          </div>

          <div class="form-check">
              <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1">
              <label class="form-check-label" for="flexRadioDefault2">
                  男
              </label>
          </div>
          <div class="form-check">
              <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2" checked>
              <label class="form-check-label" for="flexRadioDefault2">
                  女
              </label>
          </div>

          <button type="submit" class="btn btn-primary">提交</button>
      </form>
    </div>

    <div class="bd-example">

        <form>

            <h1>聊天优化</h1>

            <div class="form-check">
                <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault" checked>
                <label class="form-check-label" for="flexCheckDefault">
                    让AI在聊天时逐渐记录你的信息
                </label>
            </div>
            <div class="form-check">
                <input class="form-check-input" type="checkbox" value="" id="flexCheckChecked">
                <label class="form-check-label" for="flexCheckChecked">
                    让AI回主动提问
                </label>
            </div>
            <div class="form-check">
                <input class="form-check-input" type="checkbox" value="" id="flexCheckChecked">
                <label class="form-check-label" for="flexCheckChecked">
                    优化说话的语气
                </label>
            </div>

        </form>

    </div>
</template>

<script>
export default {
    name: "BotSetup"
}
</script>

<style scoped>

  .bd-example {
      padding: 1.5rem;
      margin-right: 0;
      margin-left: 0;
      border-width: 1px;
      border-top-left-radius: 0.25rem;
      border-top-right-radius: 0.25rem;
  }

</style>