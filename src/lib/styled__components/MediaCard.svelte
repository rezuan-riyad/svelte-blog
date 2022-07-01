<script>
  let username = 'Jane Doe';
  let designation = 'B.Sc. in Physics';
  let title = 'Bottom Aligned Media'
</script>

<div class="media">
  <div class="media-avatar">
    <div class="avatar">
      <img src="img.webp" alt={username} />
    </div>
  </div>
  <div class="media-body">
    <h5 class="mt-0 mb-1">{title}</h5>
    <p class="m-0 mb-2 text-secondary" style="font-size: 14px;">{username}, {designation}</p>
    <p class="para">
      Come on, let your colours burst. I can feel this light that's inside of
      me. All night they're playing, your song. From Tokyo to Mexico, to Rio.
      There’s no going back. But down to earth. Magical, colorful, Mr. Mystery,
      ee. Different DNA...<a>See More</a>
    </p>
    <div class="d-flex align-items-end justify-content-between">
      <button class="btn btn-sm mt-2" style="border: 1px solid lightgray;">Share</button>
      <span title="Add To Favourite" style="cursor: pointer; z-index: -1;">
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
    display: flex;
    flex-direction: row;
    align-items: flex-end;
    padding: 1rem;
    border: 1px solid lightgray;
    border-radius: 8px;
    margin-top: 1rem;
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
