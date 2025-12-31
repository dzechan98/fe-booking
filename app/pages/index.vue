<template>
  <div>
    <!-- HERO -->
    <section class="relative bg-slate-50 dark:bg-slate-900">
      <div class="max-w-7xl mx-auto px-6 py-24 grid lg:grid-cols-2 gap-12 items-center">
        <div>
          <h1 class="text-4xl md:text-5xl font-bold text-slate-900 dark:text-white leading-tight">
            Đặt Phòng Họp Nội Bộ <br />
            Cho Công Ty
          </h1>

          <p class="mt-6 text-lg text-slate-600 dark:text-slate-300">
            Hệ thống giúp nhân viên đặt phòng họp, theo dõi lịch họp và sử dụng không gian làm việc
            chung một cách
            <span class="font-semibold text-blue-600">nhanh chóng – chính xác – tiện lợi</span>.
          </p>

          <div class="mt-8">
            <NuxtLink to="/login">
              <Button label="Đăng nhập hệ thống" type="primary" full />
            </NuxtLink>
          </div>
        </div>

        <!-- HERO ILLUSTRATION -->
        <div class="hidden lg:flex justify-center">
          <div
            class="w-96 h-96 rounded-3xl bg-gradient-to-br from-blue-600 to-indigo-600 flex items-center justify-center shadow-2xl"
          >
            <i class="pi pi-building text-white text-8xl opacity-40"></i>
          </div>
        </div>
      </div>
    </section>

    <!-- BENEFITS -->
    <section class="max-w-7xl mx-auto px-6 py-16">
      <div class="grid md:grid-cols-3 gap-8 text-center">
        <div v-for="item in benefits" :key="item.title">
          <i :class="`pi ${item.icon} text-4xl text-blue-600 mb-4`"></i>
          <h3 class="text-xl font-semibold text-slate-900 dark:text-white">
            {{ item.title }}
          </h3>
          <p class="mt-2 text-slate-600 dark:text-slate-400">
            {{ item.description }}
          </p>
        </div>
      </div>
    </section>

    <!-- FEATURES -->
    <section class="bg-slate-100 dark:bg-slate-800 py-20">
      <div class="max-w-7xl mx-auto px-6">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-bold text-slate-900 dark:text-white">Tính Năng Nổi Bật</h2>
          <p class="mt-3 text-slate-600 dark:text-slate-400">
            Đáp ứng đầy đủ nhu cầu đặt phòng và quản lý nội bộ
          </p>
        </div>

        <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
          <Card
            v-for="feature in features"
            :key="feature.title"
            class="border border-slate-200 dark:border-slate-700"
          >
            <template #content>
              <div class="text-center">
                <i :class="`pi ${feature.icon} text-3xl text-blue-600 mb-3`"></i>
                <h4 class="font-semibold text-slate-900 dark:text-white">
                  {{ feature.title }}
                </h4>
                <p class="mt-2 text-sm text-slate-600 dark:text-slate-400">
                  {{ feature.description }}
                </p>
              </div>
            </template>
          </Card>
        </div>
      </div>
    </section>

    <!-- STATS -->
    <section class="max-w-7xl mx-auto px-6 py-16">
      <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
        <div v-for="stat in stats" :key="stat.label">
          <p class="text-4xl font-bold text-blue-600">
            {{ stat.number }}
          </p>
          <p class="mt-2 text-slate-600 dark:text-slate-400">
            {{ stat.label }}
          </p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import Button from '~/components/Button.vue';

const benefits = [
  {
    icon: 'pi-clock',
    title: 'Tiết kiệm thời gian',
    description: 'Không còn đặt phòng thủ công hay trùng lịch họp',
  },
  {
    icon: 'pi-eye',
    title: 'Minh bạch & rõ ràng',
    description: 'Theo dõi trạng thái phòng họp theo thời gian thực',
  },
  {
    icon: 'pi-cog',
    title: 'Quản lý tập trung',
    description: 'Dễ dàng quản lý phòng, thiết bị và người dùng',
  },
];

const features = [
  {
    icon: 'pi-calendar',
    title: 'Đặt phòng nhanh',
    description: 'Chỉ với vài thao tác là hoàn tất đặt phòng',
  },
  {
    icon: 'pi-chart-line',
    title: 'Báo cáo & thống kê',
    description: 'Theo dõi tần suất sử dụng phòng họp',
  },
  {
    icon: 'pi-desktop',
    title: 'Quản lý thiết bị',
    description: 'Máy chiếu, TV, bảng họp đi kèm phòng',
  },
  {
    icon: 'pi-users',
    title: 'Phân quyền người dùng',
    description: 'Nhân viên, quản lý, admin rõ ràng',
  },
];

const stats = [
  { number: '300+', label: 'Phòng họp' },
  { number: '8.000+', label: 'Lượt đặt mỗi tháng' },
  { number: '99%', label: 'Độ ổn định' },
  { number: '24/7', label: 'Hỗ trợ kỹ thuật' },
];
</script>
