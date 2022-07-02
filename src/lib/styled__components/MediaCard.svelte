<script>
  let username = "Jane Doe";
  let designation = "B.Sc. in Physics";
  let title = "Bottom Aligned Media";
</script>

<div class="media d-flex align-items-sm-end flex-column flex-sm-row">
  <div class="d-flex flex-row align-items-end">
    <div class="media-avatar">
      <div class="avatar">
        <img src="img.webp" alt={username} />
      </div>
    </div>
    <!-- Author Info for small screen -->
    <div class="d-sm-none">
      <h5 class="mt-0 mb-1">{title}</h5>
      <p class="m-0 text-secondary" style="font-size: 14px;">
        {username}, {designation}
      </p>
    </div>
  </div>
  <div class="media-body mt-2 mt-sm-0">
    <!-- Author Info for large screen -->
    <div class="d-none d-sm-block">
      <h5 class="mt-0 mb-1">{title}</h5>
      <p class="m-0 mb-2 text-secondary" style="font-size: 14px;">
        {username}, {designation}
      </p>
    </div>
    <p class="para">
      Come on, let your colours burst. I can feel this light that's inside of
      me. All night they're playing, your song. From Tokyo to Mexico, to Rio.
      There’s no going back. But down to earth. Magical, colorful, Mr. Mystery,
      ee. Different DNA...<a>See More</a>
    </p>
    <div class="d-flex align-items-end justify-content-between">
      <button class="btn btn-sm mt-2" style="border: 1px solid lightgray;"
        >Share</button
      >
      <span title="Add To Favourite" style="cursor: pointer; z-index: 0;">
        <ion-icon
          name="heart-sharp"
          title="Add To Favourite"
          style="font-size: 24px; pointer-events:none;"
        />
      </span>
    </div>
  </div>
</div>

<style>
  .media {
    /* display: flex;
    flex-direction: row;
    align-items: flex-end; */
    padding: 1rem;
    /* border: 1px solid #eee; */
    box-shadow: 0px 0px 4px lightgray;
    border-radius: 8px;
    margin-top: 1rem;
    background-color: white;
  }
  .avatar {
    width: 64px;
    height: 64px;
    background-color: gray;
    overflow: hidden;
    margin-right: 1rem;
  }
  .avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .para {
    margin-bottom: 0;
    line-height: 1.4rem;
    font-size: 0.95rem;
  }
</style>
