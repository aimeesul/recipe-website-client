<script>
</script>

<div class="outer">
  <div>
    <div class="title">
      RecipeShare
      <svg
        data-name="Layer 1"
        version="1.1"
        viewBox="0 0 78.22 37.94"
        xmlns="http://www.w3.org/2000/svg"
      >
        <defs>
          <style>
            .cls-1,
            .cls-2,
            .cls-3 {
              stroke: #293845;
            }
            .cls-1 {
              stroke-linecap: round;
            }
            .cls-1,
            .cls-3 {
              stroke-miterlimit: 10;
              stroke-width: 3px;
            }
            .cls-2 {
              stroke-miterlimit: 10;
              stroke-width: 3px;
            }
          </style>
        </defs>
        <g transform="translate(-.31634 -.34592)" data-name="Group 392">
          <g data-name="Group 391">
            <g transform="translate(-2.4716 -11.214)" data-name="Group 389">
              <path
                class="cls-1"
                d="m17.94 25.06a22.93 22.93 0 0 0 0-12"
                data-name="Path 232"
              />
              <path
                class="cls-1"
                d="m29.18 31a22.72 22.72 0 0 1 0-12"
                data-name="Path 233"
              />
            </g>
            <g transform="translate(-2.4716 -11.214)" data-name="Group 390">
              <path
                class="cls-1"
                d="m38.2 25.06a22.72 22.72 0 0 0 0-12"
                data-name="Path 234"
              />
              <path
                class="cls-1"
                d="m49.44 31a22.93 22.93 0 0 1 0-12"
                data-name="Path 235"
              />
            </g>
            <path
              class="cls-3"
              d="m58.048 24.686a0.86 0.86 0 0 1 0.86 0.85v0.06a12.13 12.13 0 0 1-12.11 11.19h-32.88a12.14 12.14 0 0 1-12.1-11.19 0.85 0.85 0 0 1 0.79-0.91z"
              fill="none"
              data-name="Path 236"
            />
            <path
              class="cls-2"
              d="m74.769 19.852c-0.15041 8.45e-4 -0.30385 0.01674-0.45703 0.04883l-16.031 3.3574h0.41797a0.86 0.86 0 0 1 0.86133 0.84961v0.06055a12.13 12.13 0 0 1-0.91406 3.6406l16.596-3.4746c1.2254-0.25668 2.0047-1.4503 1.748-2.6758l-2e-3 -0.0098c-0.22455-1.0722-1.1659-1.8028-2.2187-1.7968z"
              fill="none"
              stroke="#7f2629"
              stroke-miterlimit="10"
              stroke-width="3px"
            />
          </g>
        </g>
      </svg>
    </div>
    <div class="strapline">The social media for recipe sharing</div>
  </div>
  <div>
    <slot />
  </div>
</div>

<style>
  .outer {
    background-color: #b2acfa;
    width: 100%;
    padding: 1em;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    box-sizing: border-box;
  }
  .title {
    font-size: 20px;
    font-weight: bold;
  }
  .strapline {
    font-size: 14px;
  }
  svg {
    width: 60px  ;
  }
</style>
