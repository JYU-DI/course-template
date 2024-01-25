```{settings=""}
description: "Course style"
```

#- {allowangular="true"}
<tim-style-preview></tim-style-preview>

## Variables

```scss
$section-nav-dropdown-width: 300px;
```

## Main style

#-
Helpers

```scss
@mixin make_callout($name, $title, $callout_col) {
    {$ raw $}
    div.#{$name} {
        padding: 1em;
        margin-top: 1.5em;
        margin-bottom: 1.5em;
        background-color: $callout_col;
        border-left: 7px solid darken($callout_col, 40%);

        &::before {
            content: $title;
            text-transform: uppercase;
            font-weight: bold;
            color: darken($callout_col, 70%);
        }
    }
    {$ endraw $}
}

@include make_callout("Note", "Huom", #e8f8ff);
@include make_callout("Warning", "Hox!", #fff8e1);
```

```scss
@mixin post-all {
```

### Base style

```scss
.smalltext a {
    font-size: small;
}

a.smalltext a {
    font-size: 10px;
}

@media only screen and (min-width: 1024px) {
    .coursemenubar:hover {
        display: block;
        font-size: small;
    }

    .coursemenubar {
        /*position: fixed;*/
        top: 0;
        background: aliceblue;
        /*z-index: 10000;*/
    }

    .siteheader {
        margin-top: 0;
    }
}
```

#-
Scroll bar

```scss
::-webkit-scrollbar {
    width: 5px;
    height: 5px;
}

::-webkit-scrollbar-thumb {
    background-color: #888;
}

::-webkit-scrollbar-thumb:horizontal {
    background-color: #888;
}
```

#-
Main content

```scss
.par.section-top {
    margin-top: -90px !important;
}
```

#-
TIM Menu

```scss
.material-menu.timMenu {
    margin: 0 !important;
    padding: 0 !important;

    .tim-menu {
        color: #6276ad !important;
    }
    .t-icon {
        filter: invert(45%) sepia(51%) saturate(376%) hue-rotate(186deg)
            brightness(92%) contrast(93%);
    }

    .link-item.active:not(.disabled) {
        color: #002957 !important;
        border-bottom: 4px solid #002957;
        padding-bottom: 0px;

        .t-icon {
            filter: invert(14%) sepia(95%) saturate(881%) hue-rotate(182deg)
                brightness(96%) contrast(112%);
        }
    }

    .link-item:hover {
        color: #364e81 !important;
        border-bottom: 4px solid #364e81;
        padding-bottom: 0px;

        .t-icon {
            filter: invert(30%) sepia(15%) saturate(1827%) hue-rotate(182deg)
                brightness(93%) contrast(94%);
        }
    }

    .link-item.disabled {
        pointer-events: none;
        color: #ebebeb;
        .t-icon {
            filter: invert(99%) sepia(3%) saturate(258%) hue-rotate(237deg)
                brightness(116%) contrast(84%);
        }
    }

    tim-menu-runner > div {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;

        & > * {
            flex: 1;

            & > .btn-group {
                width: 100%;
            }
        }
    }

    .link-item {
        display: flex;
        align-items: center;
        gap: 1em;
        padding-left: 0.5em;
        padding-right: 0.5em;
        padding-bottom: 4px;
        padding-top: 4px;
        text-decoration: none !important;

        img,
        .t-icon {
            margin: 0;
        }

        .link-text {
            text-wrap: nowrap;
        }

        @media screen and (max-width: 724px) {
            justify-content: center;

            .link-text {
                display: none;
            }
        }
    }

    .tim-menu-links .link-item {
        border-left: 1px solid #6276ad;
        border-right: 1px solid #6276ad;
        margin-right: -1px;
    }
}

.t-icon {
    display: inline-block;
    width: 28px;
    height: 28px;
    margin: 2px !important;
    background-size: cover;

    &.t-icon-book {
        width: 24px;
        background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgNDQ4IDUxMiI+PCEtLSEgRm9udCBBd2Vzb21lIEZyZWUgNi40LjIgYnkgQGZvbnRhd2Vzb21lIC0gaHR0cHM6Ly9mb250YXdlc29tZS5jb20gTGljZW5zZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tL2xpY2Vuc2UgKENvbW1lcmNpYWwgTGljZW5zZSkgQ29weXJpZ2h0IDIwMjMgRm9udGljb25zLCBJbmMuIC0tPjxwYXRoIGQ9Ik05NiAwQzQzIDAgMCA0MyAwIDk2VjQxNmMwIDUzIDQzIDk2IDk2IDk2SDM4NGgzMmMxNy43IDAgMzItMTQuMyAzMi0zMnMtMTQuMy0zMi0zMi0zMlYzODRjMTcuNyAwIDMyLTE0LjMgMzItMzJWMzJjMC0xNy43LTE0LjMtMzItMzItMzJIMzg0IDk2em0wIDM4NEgzNTJ2NjRIOTZjLTE3LjcgMC0zMi0xNC4zLTMyLTMyczE0LjMtMzIgMzItMzJ6bTMyLTI0MGMwLTguOCA3LjItMTYgMTYtMTZIMzM2YzguOCAwIDE2IDcuMiAxNiAxNnMtNy4yIDE2LTE2IDE2SDE0NGMtOC44IDAtMTYtNy4yLTE2LTE2em0xNiA0OEgzMzZjOC44IDAgMTYgNy4yIDE2IDE2cy03LjIgMTYtMTYgMTZIMTQ0Yy04LjggMC0xNi03LjItMTYtMTZzNy4yLTE2IDE2LTE2eiIvPjwvc3ZnPg==);
    }

    &.t-icon-film {
        background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiI+PCEtLSEgRm9udCBBd2Vzb21lIEZyZWUgNi40LjIgYnkgQGZvbnRhd2Vzb21lIC0gaHR0cHM6Ly9mb250YXdlc29tZS5jb20gTGljZW5zZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tL2xpY2Vuc2UgKENvbW1lcmNpYWwgTGljZW5zZSkgQ29weXJpZ2h0IDIwMjMgRm9udGljb25zLCBJbmMuIC0tPjxwYXRoIGQ9Ik0wIDk2QzAgNjAuNyAyOC43IDMyIDY0IDMySDQ0OGMzNS4zIDAgNjQgMjguNyA2NCA2NFY0MTZjMCAzNS4zLTI4LjcgNjQtNjQgNjRINjRjLTM1LjMgMC02NC0yOC43LTY0LTY0Vjk2ek00OCAzNjh2MzJjMCA4LjggNy4yIDE2IDE2IDE2SDk2YzguOCAwIDE2LTcuMiAxNi0xNlYzNjhjMC04LjgtNy4yLTE2LTE2LTE2SDY0Yy04LjggMC0xNiA3LjItMTYgMTZ6bTM2OC0xNmMtOC44IDAtMTYgNy4yLTE2IDE2djMyYzAgOC44IDcuMiAxNiAxNiAxNmgzMmM4LjggMCAxNi03LjIgMTYtMTZWMzY4YzAtOC44LTcuMi0xNi0xNi0xNkg0MTZ6TTQ4IDI0MHYzMmMwIDguOCA3LjIgMTYgMTYgMTZIOTZjOC44IDAgMTYtNy4yIDE2LTE2VjI0MGMwLTguOC03LjItMTYtMTYtMTZINjRjLTguOCAwLTE2IDcuMi0xNiAxNnptMzY4LTE2Yy04LjggMC0xNiA3LjItMTYgMTZ2MzJjMCA4LjggNy4yIDE2IDE2IDE2aDMyYzguOCAwIDE2LTcuMiAxNi0xNlYyNDBjMC04LjgtNy4yLTE2LTE2LTE2SDQxNnpNNDggMTEydjMyYzAgOC44IDcuMiAxNiAxNiAxNkg5NmM4LjggMCAxNi03LjIgMTYtMTZWMTEyYzAtOC44LTcuMi0xNi0xNi0xNkg2NGMtOC44IDAtMTYgNy4yLTE2IDE2ek00MTYgOTZjLTguOCAwLTE2IDcuMi0xNiAxNnYzMmMwIDguOCA3LjIgMTYgMTYgMTZoMzJjOC44IDAgMTYtNy4yIDE2LTE2VjExMmMwLTguOC03LjItMTYtMTYtMTZINDE2ek0xNjAgMTI4djY0YzAgMTcuNyAxNC4zIDMyIDMyIDMySDMyMGMxNy43IDAgMzItMTQuMyAzMi0zMlYxMjhjMC0xNy43LTE0LjMtMzItMzItMzJIMTkyYy0xNy43IDAtMzIgMTQuMy0zMiAzMnptMzIgMTYwYy0xNy43IDAtMzIgMTQuMy0zMiAzMnY2NGMwIDE3LjcgMTQuMyAzMiAzMiAzMkgzMjBjMTcuNyAwIDMyLTE0LjMgMzItMzJWMzIwYzAtMTcuNy0xNC4zLTMyLTMyLTMySDE5MnoiLz48L3N2Zz4=);
    }

    &.t-icon-pen-ruler {
        background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiI+PCEtLSEgRm9udCBBd2Vzb21lIEZyZWUgNi40LjIgYnkgQGZvbnRhd2Vzb21lIC0gaHR0cHM6Ly9mb250YXdlc29tZS5jb20gTGljZW5zZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tL2xpY2Vuc2UgKENvbW1lcmNpYWwgTGljZW5zZSkgQ29weXJpZ2h0IDIwMjMgRm9udGljb25zLCBJbmMuIC0tPjxwYXRoIGQ9Ik00NjkuMyAxOS4zbDIzLjQgMjMuNGMyNSAyNSAyNSA2NS41IDAgOTAuNWwtNTYuNCA1Ni40TDMyMi4zIDc1LjdsNTYuNC01Ni40YzI1LTI1IDY1LjUtMjUgOTAuNSAwek00NC45IDM1My4yTDI5OS43IDk4LjMgNDEzLjcgMjEyLjMgMTU4LjggNDY3LjFjLTYuNyA2LjctMTUuMSAxMS42LTI0LjIgMTQuMmwtMTA0IDI5LjdjLTguNCAyLjQtMTcuNCAuMS0yMy42LTYuMXMtOC41LTE1LjItNi4xLTIzLjZsMjkuNy0xMDRjMi42LTkuMiA3LjUtMTcuNSAxNC4yLTI0LjJ6TTI0OS40IDEwMy40TDEwMy40IDI0OS40IDE2IDE2MS45Yy0xOC43LTE4LjctMTguNy00OS4xIDAtNjcuOUw5NC4xIDE2YzE4LjctMTguNyA0OS4xLTE4LjcgNjcuOSAwbDE5LjggMTkuOGMtLjMgLjMtLjcgLjYtMSAuOWwtNjQgNjRjLTYuMiA2LjItNi4yIDE2LjQgMCAyMi42czE2LjQgNi4yIDIyLjYgMGw2NC02NGMuMy0uMyAuNi0uNyAuOS0xbDQ1LjEgNDUuMXpNNDA4LjYgMjYyLjZsNDUuMSA0NS4xYy0uMyAuMy0uNyAuNi0xIC45bC02NCA2NGMtNi4yIDYuMi02LjIgMTYuNCAwIDIyLjZzMTYuNCA2LjIgMjIuNiAwbDY0LTY0Yy4zLS4zIC42LS43IC45LTFMNDk2IDM1MC4xYzE4LjcgMTguNyAxOC43IDQ5LjEgMCA2Ny45TDQxNy45IDQ5NmMtMTguNyAxOC43LTQ5LjEgMTguNy02Ny45IDBsLTg3LjQtODcuNEw0MDguNiAyNjIuNnoiLz48L3N2Zz4=);
    }

    &.t-icon-left {
        width: 18px;
        background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMzIwIDUxMiI+PCEtLSEgRm9udCBBd2Vzb21lIEZyZWUgNi40LjIgYnkgQGZvbnRhd2Vzb21lIC0gaHR0cHM6Ly9mb250YXdlc29tZS5jb20gTGljZW5zZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tL2xpY2Vuc2UgKENvbW1lcmNpYWwgTGljZW5zZSkgQ29weXJpZ2h0IDIwMjMgRm9udGljb25zLCBJbmMuIC0tPjxwYXRoIGQ9Ik05LjQgMjMzLjRjLTEyLjUgMTIuNS0xMi41IDMyLjggMCA0NS4zbDE5MiAxOTJjMTIuNSAxMi41IDMyLjggMTIuNSA0NS4zIDBzMTIuNS0zMi44IDAtNDUuM0w3Ny4zIDI1NiAyNDYuNiA4Ni42YzEyLjUtMTIuNSAxMi41LTMyLjggMC00NS4zcy0zMi44LTEyLjUtNDUuMyAwbC0xOTIgMTkyeiIvPjwvc3ZnPgo=);
    }

    &.t-icon-right {
        width: 18px;
        background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMzIwIDUxMiI+PCEtLSEgRm9udCBBd2Vzb21lIEZyZWUgNi40LjIgYnkgQGZvbnRhd2Vzb21lIC0gaHR0cHM6Ly9mb250YXdlc29tZS5jb20gTGljZW5zZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tL2xpY2Vuc2UgKENvbW1lcmNpYWwgTGljZW5zZSkgQ29weXJpZ2h0IDIwMjMgRm9udGljb25zLCBJbmMuIC0tPjxwYXRoIGQ9Ik0zMTAuNiAyMzMuNGMxMi41IDEyLjUgMTIuNSAzMi44IDAgNDUuM2wtMTkyIDE5MmMtMTIuNSAxMi41LTMyLjggMTIuNS00NS4zIDBzLTEyLjUtMzIuOCAwLTQ1LjNMMjQyLjcgMjU2IDczLjQgODYuNmMtMTIuNS0xMi41LTEyLjUtMzIuOCAwLTQ1LjNzMzIuOC0xMi41IDQ1LjMgMGwxOTIgMTkyeiIvPjwvc3ZnPgo=);
    }

    &.t-icon-info {
        background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiI+PCEtLSEgRm9udCBBd2Vzb21lIEZyZWUgNi40LjIgYnkgQGZvbnRhd2Vzb21lIC0gaHR0cHM6Ly9mb250YXdlc29tZS5jb20gTGljZW5zZSAtIGh0dHBzOi8vZm9udGF3ZXNvbWUuY29tL2xpY2Vuc2UgKENvbW1lcmNpYWwgTGljZW5zZSkgQ29weXJpZ2h0IDIwMjMgRm9udGljb25zLCBJbmMuIC0tPjxwYXRoIGQ9Ik0yNTYgNTEyQTI1NiAyNTYgMCAxIDAgMjU2IDBhMjU2IDI1NiAwIDEgMCAwIDUxMnpNMjE2IDMzNmgyNFYyNzJIMjE2Yy0xMy4zIDAtMjQtMTAuNy0yNC0yNHMxMC43LTI0IDI0LTI0aDQ4YzEzLjMgMCAyNCAxMC43IDI0IDI0djg4aDhjMTMuMyAwIDI0IDEwLjcgMjQgMjRzLTEwLjcgMjQtMjQgMjRIMjE2Yy0xMy4zIDAtMjQtMTAuNy0yNC0yNHMxMC43LTI0IDI0LTI0em00MC0yMDhhMzIgMzIgMCAxIDEgMCA2NCAzMiAzMiAwIDEgMSAwLTY0eiIvPjwvc3ZnPg==);
    }
}

.menu-next-prev-nav.timMenu {
    .tim-menu-links .link-item {
        border-left: none;
        border-right: none;
        margin-right: 0;
    }

    .tim-menu-links:first-child .link-item {
        justify-content: start;
    }

    .tim-menu-links:last-child .link-item {
        justify-content: end;
    }

    tim-menu-runner > div {
        flex-wrap: nowrap;
    }

    .link-item .link-text {
        text-wrap: balance;
    }
}

.menu-no-top .tim-menu {
    padding-top: 0 !important;
    margin-top: 0 !important;
}

.menu-no-bottom .tim-menu {
    padding-bottom: 0 !important;
    margin-bottom: 0 !important;
}
```

#-
Chapter navigation

```scss
.section-nav {
    z-index: 1001 !important;
    padding: 0 !important;
    .tim-menu {
        font-size: 14px !important;
        display: flex;
        flex-wrap: wrap;
        gap: 24px;
        justify-content: space-between;
        user-select: none;
        padding-bottom: 0 !important;
        margin-bottom: 0 !important;
        cursor: initial !important;
    }

    .home-link,
    .chapter-name {
        padding-top: 10px;
        padding-bottom: 10px;

        color: $basic-color;

        &:hover {
            color: lighten($basic-color, 10%);
        }
    }

    .chapter-name {
        display: inline-flex;
        gap: 0.2em;
        align-items: center;
        width: $section-nav-dropdown-width;
    }

    .tim-menu-dropdown {
        width: 100%;
        box-shadow: 0 4px 6px -1px RGB(0 0 0 / 0.1), 0 2px 4px -2px RGB(0 0 0 /
                        0.1) !important;
        background-clip: border-box !important;
    }

    .tim-menu-item {
        padding: 0 !important;

        & > * {
            font-size: 14px;
            font-family: $font-family-head;
            display: block;
            width: 100%;
            padding: 8px 24px;
        }
    }
}
```

#-
Progress bar

```scss
.ch-progress-container {
    display: inline-flex;
    align-items: center;
    gap: 8px;
}

.ch-progress {
    width: 20%;
    margin-left: auto;
    background-color: #babbbf;
    display: inline-flex;
    height: 5px;

    .ch-progress-bar {
        background: $basic-color;
        width: var(--prog, 0);
    }
}
```

#-
Remove reference marker

```scss
tim-par-ref {
    display: none;
}
```

#-
Auto-scale video size

```scss
.autosize video.showVideo {
    width: 100% !important;
    height: auto !important;
}
```

```scss
.video-thumbnail i.glyphicon {
    opacity: 0.6;
    font-size: 64px;
}

.video-thumbnail .video-thumbnail-image {
    max-width: 67%;
}
```

```scss
}
```
