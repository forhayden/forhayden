---
layout: page
title: 랜덤해둔티비
permalink: /rht
---

<script>
    const container = document.createElement("div")
    const button = document.createElement("div")
    const video = document.createElement("video")
    const loading = document.createElement("p")

    const srcs = []
    for(let i=1; i<19; i++){
        srcs.push(`/forhayden/assets/video/${i}.mp4`)
    }

    const srcLength = srcs.length

    container.style.background = "white"
    container.style.margin = "0px"
    container.style.width = "-webkit-fill-available"
    container.style.height = "600px"
    container.style.position = "relative"

    container.appendChild(button)
    container.appendChild(video)
    container.appendChild(loading)
    document.getElementsByClassName("page-content").item(0).appendChild(container)

    const buttonSize = "20%"
    button.style.width = buttonSize
    button.style.height = buttonSize
    button.style.backgroundImage = "url(\"/forhayden/assets/img/button.png\")"
    button.style.backgroundRepeat = "no-repeat"
    button.style.backgroundSize = "100%"
    button.style.zIndex = "9"
    button.style.position = "absolute"
    button.style.left = "80%"
    button.style.top = "80%"

    button.addEventListener("click", Play)

    loading.style.position = "absolute"
    loading.innerText = "해두니 달려오는 중..."
    loading.style.width = "-webkit-fill-available"
    loading.style.height = buttonSize
    loading.style.zIndex = "9"
    loading.style.color = "white"
    loading.style.top = "45%"
    loading.style.left = "40%"
    loading.style.display = "block"

    video.src = srcs[parseInt(Math.random() * srcLength)]
    video.muted = true
    video.crossOrigin = "anonymous"
    video.style.width = "-webkit-fill-available"
    video.style.height = "600px"
    video.style.position = "absolute"
    video.playsInline = true
    video.setAttribute("playsinline","null")

    video.addEventListener("ended", ()=> Play())
    video.play().then(()=> loading.style.display = "none")

    async function Play(){
        loading.style.display = "block"

        const index = parseInt(Math.random() * srcLength)

        video.src = srcs[index]
        video.muted = false
        await video.play()

        loading.style.display = "none"
    }
</script>
