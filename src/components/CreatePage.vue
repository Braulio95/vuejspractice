<template>
    <div class="container mb-3">
        <form action="">
            <div class="mb-3">
                <label for="" class="form-label"> Page Title </label>
                <input type="text" class="form-control" v-model="pageTitle" />
            </div>
            <div class="mb-3">
                <label for="" class="form-label"> Content </label>
                <textarea
                    type="text"
                    class="form-control"
                    rows="5"
                    v-model="content"
                ></textarea>
            </div>
            <div class="col">
                <div class="mb-3">
                    <label for="" class="form-label">Link text</label>
                    <input
                        type="text"
                        class="form-control"
                        v-model="linkText"
                    />
                </div>
                <div class="mb-3">
                    <label for="" class="form-label"> Link URL </label>
                    <input type="text" class="form-control" v-model="linkUrl" />
                </div>
                <div class="row mb-3">
                    <div class="form-check">
                        <input type="checkbox" class="form-check-input" />
                        <label for="gridCheck1" class="form-check-label"
                            >Published
                        </label>
                    </div>
                </div>
            </div>
            <div class="mb-3">
                <button
                    class="btn btn-primary"
                    :disabled="isFormValid"
                    @click.prevent="
                        pageCreated({ pageTitle, content, linkText, linkUrl })
                    "
                >
                    Create Page
                </button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    props: ["pageCreated"],
    computed: {
        isFormValid() {
            return;
        },
    },
    data() {
        return {
            pageTitle: "",
            content: "",
            linkText: "",
            linkUrl: "",
        };
    },
    methods: {
        sumbitForm() {
            if (
                !this.pageTitle ||
                !this.content ||
                !this.linkText ||
                !this.linkUrl
            ) {
                alert("Please fill the form");
                return;
            }
        },
    },
};
</script>
