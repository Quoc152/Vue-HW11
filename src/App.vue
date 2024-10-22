<script setup>
import { Button } from '@/components/ui/button'
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from '@/components/ui/card'
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar'
import { Input } from '@/components/ui/input'
import { Label } from '@/components/ui/label'

const user = {
  name: 'Lê Bảo Quốc',
  email: 'quocle@example.com',
  bio: 'Lập trình viên Frontend',
  location: 'Đà Nẵng, Việt Nam',
  avatarUrl: '/placeholder.svg?height=128&width=128',
  initials: 'NVA',
  posts: 42,
  followers: 1337,
  following: 123
}
</script>

<template>
  <div class="min-h-screen bg-background flex items-center justify-center p-4">
    <Card class="w-full max-w-2xl">
      <CardHeader>
        <CardTitle>Hồ sơ người dùng</CardTitle>
        <CardDescription>Xem và quản lý thông tin cá nhân của bạn</CardDescription>
      </CardHeader>
      <CardContent>
        <div class="flex flex-col md:flex-row gap-6">
          <Avatar class="w-32 h-32">
            <AvatarImage :src="user.avatarUrl" :alt="user.name" />
            <AvatarFallback>{{ user.initials }}</AvatarFallback>
          </Avatar>
          <div class="flex-1">
            <h2 class="text-2xl font-bold mb-2">{{ user.name }}</h2>
            <p class="text-muted-foreground mb-4">{{ user.bio }}</p>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div>
                <Label for="email">Email</Label>
                <Input id="email" :model-value="user.email" readonly />
              </div>
              <div>
                <Label for="location">Địa điểm</Label>
                <Input id="location" :model-value="user.location" readonly />
              </div>
            </div>
          </div>
        </div>
      </CardContent>
      <CardFooter>
        <div class="w-full grid grid-cols-3 gap-4 text-center">
          <div>
            <p class="text-2xl font-bold">{{ user.posts }}</p>
            <p class="text-muted-foreground">Bài viết</p>
          </div>
          <div>
            <p class="text-2xl font-bold">{{ user.followers }}</p>
            <p class="text-muted-foreground">Người theo dõi</p>
          </div>
          <div>
            <p class="text-2xl font-bold">{{ user.following }}</p>
            <p class="text-muted-foreground">Đang theo dõi</p>
          </div>
        </div>
      </CardFooter>
    </Card>
  </div>
</template>