<div align="center">

---

[![Twitter](https://img.shields.io/badge/-@xxxadsicekubs-0d1117?style=for-the-badge&logo=x&logoColor=white&color=000000)](https://x.com/xxxadsicekubs)
[![Discord](https://img.shields.io/badge/-@ic.ekubs__ads-0d1117?style=for-the-badge&logo=discord&logoColor=white&color=5865F2)](https://discord.com/users/1363847589899931690)
[![YouTube](https://img.shields.io/badge/-@xxxadsicekubs-0d1117?style=for-the-badge&logo=youtube&logoColor=white&color=FF0000)](https://youtube.com/@xxxadsicekubs)

---

### 📊 github stats
<img src="https://raw.githubusercontent.com/xxxadsicekubs/stats/master/generated/overview.svg#gh-dark-mode-only"/>
<img src="https://raw.githubusercontent.com/xxxadsicekubs/stats/master/generated/overview.svg#gh-light-mode-only"/>
<img src="https://raw.githubusercontent.com/xxxadsicekubs/stats/master/generated/languages.svg#gh-dark-mode-only"/>
<img src="https://raw.githubusercontent.com/xxxadsicekubs/stats/master/generated/languages.svg#gh-light-mode-only"/>

---

<div style="overflow:hidden; border-radius:30px; margin-top:-10px;">
  <img width="100%" 
       src="https://capsule-render.vercel.app/api?type=waving&color=0:080d1e,50:0d2137,100:080d1e&height=120&section=footer"/>
</div>

<a href="https://discord.com/users/1363847589899931690" style="display:block; position:relative;">
  <img src="https://lanyard-profile-readme.vercel.app/api/1363847589899931690?theme=dark&bg=080d1e&animated=true&hideDiscrim=true&borderRadius=30px&idleMessage=M%20V%20P" 
       style="display:block; border-radius:30px; margin-bottom:0; width:150px; height:150px;">
  
  <span id="discord-status" 
        style="position:absolute; bottom:10px; left:10px; padding:4px 8px; background:rgba(0,0,0,0.6); color:white; font-size:12px; font-family:sans-serif; border-radius:12px; display:flex; align-items:center;">
    <img id="status-icon" src="https://cdn.jsdelivr.net/npm/discord-status-icons@1.0.0/online.svg" width="14" style="margin-right:6px;">
    กำลังโหลด...
  </span>
</a>

<div style="overflow:hidden; border-radius:30px; margin-top:-10px;">
  <img width="100%" 
       src="https://capsule-render.vercel.app/api?type=waving&color=0:080d1e,50:0d2137,100:080d1e&height=120&section=footer"/>
</div>

---

<div style="max-width:350px; margin:auto; font-family:sans-serif; position:relative;">

  <!-- Avatar Discord -->
  <a href="https://discord.com/users/1363847589899931690" style="display:block; position:relative; z-index:2;">
    <img src="https://lanyard-profile-readme.vercel.app/api/1363847589899931690?theme=dark&bg=080d1e&animated=true&hideDiscrim=true&borderRadius=30px&idleMessage=M%20V%20P" 
         style="display:block; border-radius:30px; width:100%; box-shadow:0 10px 20px rgba(0,0,0,0.5);">
  </a>

  <!-- Capsule Render Background -->
  <div style="overflow:hidden; border-radius:30px; margin-top:-20px; position:relative; z-index:1;">
    <img width="100%" 
         src="https://capsule-render.vercel.app/api?type=waving&color=0:080d1e,50:0d2137,100:080d1e&height=140&section=footer" 
         style="display:block;">
    
    <!-- Floating Activity Overlay -->
    <div id="discord-activity" 
         style="position:absolute; bottom:10px; left:50%; transform:translateX(-50%); 
                background:rgba(0,0,0,0.6); color:white; padding:6px 12px; border-radius:20px; 
                display:flex; align-items:center; font-size:13px; font-weight:bold;
                animation: float 2s ease-in-out infinite alternate;">
      <img id="activity-icon" src="https://cdn.jsdelivr.net/npm/discord-status-icons@1.0.0/online.svg" width="16" style="margin-right:8px;">
      กำลังโหลด...
    </div>
  </div>
</div>

<!-- Animation CSS -->
<style>
  @keyframes float {
    0% { transform: translateX(-50%) translateY(0px); }
    100% { transform: translateX(-50%) translateY(-6px); }
  }
</style>

<!-- Script ดึงสถานะและ Activity จาก Lanyard API -->
<script>
fetch('https://api.lanyard.rest/v1/users/1363847589899931690')
  .then(res => res.json())
  .then(data => {
    const discordStatus = data.data.discord_status; // online, idle, dnd, offline
    const activities = data.data.activities; // array ของ activities

    const statusIcons = {
      online: 'https://cdn.jsdelivr.net/npm/discord-status-icons@1.0.0/online.svg',
      idle: 'https://cdn.jsdelivr.net/npm/discord-status-icons@1.0.0/idle.svg',
      dnd: 'https://cdn.jsdelivr.net/npm/discord-status-icons@1.0.0/dnd.svg',
      offline: 'https://cdn.jsdelivr.net/npm/discord-status-icons@1.0.0/offline.svg'
    };

    const activityElement = document.getElementById('discord-activity');
    const activityIcon = document.getElementById('activity-icon');

    activityIcon.src = statusIcons[discordStatus] || statusIcons.offline;

    if (activities && activities.length > 0) {
      const activity = activities[0];
      // ถ้า activity มี detail เช่นเล่นเกม / ฟังเพลง
      activityElement.innerHTML = `<img src="${activityIcon.src}" width="16" style="margin-right:8px;">${activity.name}${activity.details ? ' - '+activity.details : ''}`;
    } else {
      activityElement.innerHTML = `<img src="${activityIcon.src}" width="16" style="margin-right:8px;">ไม่ได้ทำอะไรอยู่ตอนนี้`;
    }
  })
  .catch(err => {
    console.error(err);
    const activityElement = document.getElementById('discord-activity');
    activityElement.innerHTML = 'ไม่สามารถโหลดสถานะได้';
  });
</script>
