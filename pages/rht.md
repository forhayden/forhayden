---
layout: page
title: 랜덤해둔티비
permalink: /rht
---

<script>
    const container = document.createElement("div")
    const button = document.createElement("div")
    const video = document.createElement("video")

    const srcs = []
    for(let i=1; i<19; i++){
        srcs.push(`/forhayden/assets/video/${i}.mp4`)
    }

    const srcLength = srcs.length

    container.style.background = "black"
    container.style.margin = "0px"
    container.style.width = "-webkit-fill-available"
    container.style.height = "500px"
    container.style.position = "relative"

    container.appendChild(button)
    container.appendChild(video)
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

    button.addEventListener("click", ()=>{
        const index = parseInt(Math.random() * srcLength)

        video.src = srcs[index]
        video.muted = false
        video.play()
    })

    video.src = srcs[parseInt(Math.random() * srcLength)]
    video.muted = true
    video.autoplay = true
    video.style.width = "-webkit-fill-available"
    video.style.height = "-webkit-fill-available"
    video.style.position = "absolute"
</script>
