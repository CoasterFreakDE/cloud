<template>
  <ul data-v-418b01c5="" class="statuses">
    <div data-v-418b01c5="" id="status-status">
      <li data-v-73d0e1b7="">
        <div data-v-73d0e1b7="" class="user-status-menu-item">
          <!---->
          <button
            data-v-73d0e1b7=""
            href="#"
            class="
              user-status-menu-item__toggle
              user-status-menu-item__toggle--inline
            "
          >
            <span
              data-v-73d0e1b7=""
              class="user-status-menu-item__toggle-icon icon-user-status-online"
            ></span>
            Status setzen
          </button>
        </div>
        <!---->
      </li>
    </div>
    <div data-v-418b01c5="" id="status-weather">
      <li class="inline">
        <div id="weather-status-menu-item">
          <div
            data-v-54ba527a=""
            class="action-item weather-status-menu-item__subheader"
          >
            <div
              data-v-54ba527a=""
              class="v-popover"
              delay="0"
              handle-resize="true"
              placement="bottom"
              boundaries-element="[object HTMLBodyElement]"
              container="body"
            >
              <div class="trigger" style="display: inline-block">
                <button
                  data-v-54ba527a=""
                  aria-label="Aktionen"
                  aria-haspopup="true"
                  aria-controls="menu-khjqi"
                  test-attr="1"
                  aria-expanded="false"
                  class="
                    icon
                    action-item__menutoggle
                    icon-cloudy
                    action-item__menutoggle--with-title
                  "
                >
                  21.6 °C Bewölkt um 12:00
                </button>
              </div>
            </div>
          </div>
        </div>
      </li>
    </div>
  </ul>
</template>
<style lang="scss" scoped>
.statuses {
	display: flex;
	flex-direction: row;
	justify-content: center;
	flex-wrap: wrap;
	margin-bottom: 36px;

	& > div {
		margin: 8px;
	}
  & button {
    text-align: center;
  background: white;
  min-width: 44px;
  height: 40px;
  border-radius: 10px;
  width: auto;
  padding: 5px 5px 5px 5px;
  }
}
</style>