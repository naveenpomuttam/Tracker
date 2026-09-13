// sw.js - Service Worker for Background Notifications

self.addEventListener('install', (event) => {
  self.skipWaiting();
});

self.addEventListener('activate', (event) => {
  event.waitUntil(self.clients.claim());
});

// PWA ബാക്ക്ഗ്രൗണ്ടിൽ ആയിരിക്കുമ്പോൾ നോട്ടിഫിക്കേഷൻ കാണിക്കാൻ
self.addEventListener('message', (event) => {
  if (event.data && event.data.type === 'SHOW_NOTIFICATION') {
    self.registration.showNotification(event.data.title, {
      body: event.data.body,
      icon: 'https://cdn-icons-png.flaticon.com/512/3448/3448339.png',
      vibrate: [200, 100, 200],
      tag: 'geofence-alert'
    });
  }
});
