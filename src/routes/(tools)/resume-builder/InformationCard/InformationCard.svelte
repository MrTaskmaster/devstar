<script lang="ts">
    import { clickedBtn } from "../ProfileCard/ClickedButton";
    import EducationFrame from "./EducationFrame.svelte";
    import EducationTextTile from "./EducationTextTile.svelte";
    import WorkExperienceMiddleTile from "./WorkExperienceMiddleTile.svelte";
    import WorkExperienceTile from "./WorkExperienceTile.svelte";
    import ProjectMiddleTile from "./ProjectMiddleTile.svelte";
    import ProjectTextTile from "./ProjectTextTile.svelte";
    import AchievementDetailsMiddleTile from "./achievementDetailsMiddleTile.svelte";
    import AchievementTile from "./AchievementTile.svelte";
    import SkillsMiddleTile from "./skillsMiddleTile.svelte";
    import SkillsTextTile from "./SkillsTextTile.svelte";
    import CertificationDetailsMiddleTile from "./certificationDetailsMiddleTile.svelte";
    import CertficationTile from "./CertficationTile.svelte";
    import { achievementStore } from "./AchievementStore";
    import { EducationStore } from "./EducationStore";
    import {WorkExpStore} from "./workExp";
    import { projectStore } from "./projectStore";
    import { SkillsStore } from "./SkillsStore";
    import { Certificationstore } from "./Certificationstore";
</script>
{#if $clickedBtn ==="Education"}
    <EducationFrame/>
    {#if $EducationStore.length > 0}
        {#each $EducationStore as {id} (id)}
        <EducationTextTile idfordetail={id}/>
        {/each}
    {/if}
{:else if $clickedBtn === "Experience"}
    <WorkExperienceMiddleTile/>
    {#if $WorkExpStore.length > 0}
        {#each $WorkExpStore as {id} (id)}
        <WorkExperienceTile idfordetail={id}/>
        {/each}
    {/if}
{:else if $clickedBtn === "Projects"}
    <ProjectMiddleTile/>
    {#if $projectStore.length > 0}
        {#each $projectStore as {id} (id)}
        <ProjectTextTile idfordetail={id}/>
        {/each}
    {/if}
{:else if $clickedBtn === "Achievements"}
    <AchievementDetailsMiddleTile/>
    {#if $achievementStore.length > 0}
        {#each $achievementStore as {id, achievementName, achievementLink} (id)}
        <AchievementTile achieve={achievementName} link={achievementLink} idfordetail={id}/>
        {/each}
    {/if}
{:else if $clickedBtn === "Skills"}
    <SkillsMiddleTile/>
    {#if $SkillsStore.techSkills.length >0 || $SkillsStore.softSkills.length >0}
        <SkillsTextTile/>
    {/if}
{:else if $clickedBtn === "Certifications"}
    <CertificationDetailsMiddleTile/>
    {#if $Certificationstore.length > 0}
        {#each $Certificationstore as {id} (id)}
        <CertficationTile idfordetail={id}/>
        {/each}
    {/if}
{/if}