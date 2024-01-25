```{settings=""}
description: "DI Coure Home Page"
```

```scss
$paragraph-preferred-width: 100%;
$section-width: 1000px;
$paragraph-mobile-width: $section-width;

@mixin post-all {
    .material {
        background-color: white;
    }
    .paragraphs {
        background-color: transparent;
        box-shadow: none;
        padding-top: 0;
        margin-top: 0;
        padding-left: 0;
        padding-right: 0;
    }

    .par {
        margin: 0 !important;
        padding: 0 !important;
    }

    .title-content {
        padding: 0 !important;
        user-select: none;
    }

    .jumbotron-title {
        text-wrap: balance;
        color: var(--basic-color);

        h1 {
            font-size: 58px;
        }

        h1::before {
            background-color: var(--basic-color);
        }
    }

    .jumbotron-icons img {
        max-width: 200px !important;
        margin: 30px;
    }

    .info-area {
        background: var(--secondary-bg-color);
    }

    .task-area-inverted {
        max-width: $section-width;
        padding-top: 45px;
        padding-bottom: 50px;
        .parContent {
            font-size: 1.3em;
        }
    }

    .section-container {
        max-width: $section-width;
        margin-left: auto !important;
        margin-right: auto !important;
    }

    [data-area^="progress-section"] {
        max-width: 1400px;
        margin: auto !important;
        &.areacollapse,
        &.areaexpand {
            margin-top: 20px !important;

            display: flex;
            gap: 12px;
            padding-left: 12px !important;
            padding-right: 12px !important;
            flex-direction: row;
            align-items: center;
            height: 64px;
            user-select: none;

            background-color: $primary-bg-color;
            box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 1px -1px, rgba(0, 0, 0, 0.14)
                    0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
            border-radius: 4px;

            .areatoggle {
                position: initial;
                order: 9999;
                margin-left: auto;
                font-size: 14px;

                // Override into chevron-down
                &.glyphicon-plus::before {
                    content: "\e114";
                }

                // Override into chevron-up
                &.glyphicon-minus::before {
                    content: "\e113";
                }
            }

            .areatitle {
                display: inline-flex;
                align-items: center;
                flex: 1;
                gap: 12px;

                h2 {
                    font-size: 26px;
                    color: $basic-color;
                    font-weight: 500;
                    user-select: none;

                    display: flex;
                    align-items: center;
                    gap: 10px;

                    flex: 1;

                    line-height: 1.2;

                    @media screen and (max-width: 724px) {
                        font-size: 20px;
                    }
                }

                .ch-num {
                    padding-right: 6px;
                    border-right: 1px solid $basic-color;
                    display: inline-block;
                    min-width: 25px;
                }

                & > * {
                    margin-bottom: 0 !important;
                    margin-top: 0 !important;
                }
            }
        }

        &.areaContent {
            background-color: $primary-bg-color;
            width: 100%;
        }
    }

    [class*="area_progress-section"] {
        overflow: hidden;
        display: grid;
        grid-template-rows: 1fr;
        transition: grid-template-rows 300ms cubic-bezier(0.4, 0, 0.2, 1) 0ms;
        &.collapsed {
            display: grid;
            grid-template-rows: 0fr;
        }

        & > .areaContent {
            overflow: hidden;
            border-bottom-left-radius: 4px;
            border-bottom-right-radius: 4px;

            .ch-section-list .parContent,
            .ch-section-list .parContent > p {
                display: flex;
                flex-direction: column;
                padding: 24px 12px;
                gap: 8px;
                user-select: none;

                & > p {
                    padding: 0 !important;
                    margin: 0 !important;
                }

                @media screen and (max-width: 724px) {
                    gap: 12px;
                }

                .ch-sec-url {
                    display: flex;
                    gap: 12px;
                    text-decoration: none;
                    padding-top: 4px;
                    padding-bottom: 4px;
                    padding-left: 26px;
                    padding-right: 26px;
                    transition: background-color 250ms cubic-bezier(
                                0.4,
                                0,
                                0.2,
                                1
                            ) 0ms, box-shadow 250ms cubic-bezier(0.4, 0, 0.2, 1)
                            0ms,
                        border-color 250ms cubic-bezier(0.4, 0, 0.2, 1) 0ms, color
                            250ms cubic-bezier(0.4, 0, 0.2, 1) 0ms;

                    p {
                        display: none;
                    }

                    &:hover {
                        background-color: RGB(0 41 87 / 5%);
                    }

                    .ch-sec-title {
                        font-family: $font-family-head;
                        font-weight: 500;
                        font-size: 20px;
                        margin-right: auto;
                        color: $basic-color;

                        @media screen and (max-width: 724px) {
                            font-size: 16px;
                        }
                    }

                    &.disabled {
                        pointer-events: none;
                        .ch-sec-title {
                            color: #babbbf;
                        }
                    }
                }
            }
        }
    }

    .ch-progress-num {
        color: $basic-color;
        font-size: 16px;
        width: 3em;
        text-align: right;
    }

    .headerlink {
        left: 0 !important;
    }

    .ch-progress {
        max-width: 300px !important;
        min-width: 300px !important;
        flex: 1;

        @media screen and (max-width: 724px) {
            max-width: 100px !important;
            min-width: 100px !important;
        }
    }

    // TODO: Poista
    .tg {
        border-collapse: collapse;
        border-spacing: 0;
    }
    .tg td {
        border-color: black;
        border-style: solid;
        border-width: 1px;
        font-family: Arial, sans-serif;
        font-size: 14px;
        overflow: hidden;
        padding: 10px 5px;
        word-break: normal;
    }
    .tg th {
        border-color: black;
        border-style: solid;
        border-width: 1px;
        font-family: Arial, sans-serif;
        font-size: 14px;
        font-weight: normal;
        overflow: hidden;
        padding: 10px 5px;
        word-break: normal;
    }
    .tg .tg-ltxa {
        background-color: #ffccc9;
        text-align: left;
        vertical-align: top;
    }
    .tg .tg-cyze {
        background-color: #cbcefb;
        font-weight: bold;
        text-align: left;
        vertical-align: top;
    }
    .tg .tg-0lax {
        text-align: left;
        vertical-align: top;
    }
    .tg .tg-8zwo {
        font-style: italic;
        text-align: left;
        vertical-align: top;
    }
}
```
