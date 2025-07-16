<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>禅心瑜伽 - 身心平衡的艺术</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
  
  <!-- Tailwind 配置 -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '#4A6F5B',
            secondary: '#F2E9E4',
            accent: '#9A8C98',
            neutral: '#22223B',
            light: '#F8F9FA',
          },
          fontFamily: {
            sans: ['Inter', 'system-ui', 'sans-serif'],
            serif: ['Merriweather', 'Georgia', 'serif'],
          },
          backgroundImage: {
            'hero-pattern': "linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.6)), url('https://picsum.photos/id/1019/1600/900')",
            'yoga-pose': "linear-gradient(rgba(74, 111, 91, 0.8), rgba(74, 111, 91, 0.9)), url('https://picsum.photos/id/1024/1600/900')",
          }
        },
      }
    }
  </script>
  
  <style type="text/tailwindcss">
    @layer utilities {
      .content-auto {
        content-visibility: auto;
      }
      .text-shadow {
        text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
      }
      .transition-transform-opacity {
        transition-property: transform, opacity;
        transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
        transition-duration: 500ms;
      }
      .scale-up-hover {
        transition: transform 0.3s ease;
      }
      .scale-up-hover:hover {
        transform: scale(1.03);
      }
      .nav-scrolled {
        @apply bg-primary/95 shadow-lg;
      }
      .section-fade-in {
        opacity: 0;
        transform: translateY(30px);
        transition: opacity 0.8s ease, transform 0.8s ease;
      }
      .section-fade-in.visible {
        opacity: 1;
        transform: translateY(0);
      }
    }
  </style>
</head>
<body class="bg-light font-sans text-neutral antialiased">
  <!-- 导航栏 -->
  <header id="navbar" class="fixed w-full top-0 z-50 transition-all duration-300 py-4">
    <div class="container mx-auto px-4 md:px-6">
      <nav class="flex items-center justify-between">
        <a href="#" class="flex items-center space-x-2">
          <i class="fa fa-leaf text-2xl text-secondary"></i>
          <span class="text-xl md:text-2xl font-serif font-bold text-white text-shadow">禅心瑜伽</span>
        </a>
        
        <!-- 桌面导航 -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="#home" class="text-white hover:text-secondary transition-colors duration-300">首页</a>
          <a href="#about" class="text-white hover:text-secondary transition-colors duration-300">关于我们</a>
          <a href="#classes" class="text-white hover:text-secondary transition-colors duration-300">课程</a>
          <a href="#teachers" class="text-white hover:text-secondary transition-colors duration-300">导师</a>
          <a href="#pricing" class="text-white hover:text-secondary transition-colors duration-300">价格</a>
          <a href="#contact" class="bg-secondary text-primary px-5 py-2 rounded-full hover:bg-opacity-80 transition-all duration-300">预约体验</a>
        </div>
        
        <!-- 移动端菜单按钮 -->
        <button id="menu-toggle" class="md:hidden text-white text-2xl focus:outline-none">
          <i class="fa fa-bars"></i>
        </button>
      </nav>
      
      <!-- 移动端导航菜单 -->
      <div id="mobile-menu" class="md:hidden hidden bg-white rounded-lg shadow-xl mt-4 p-4 absolute left-4 right-4 transition-all duration-300">
        <div class="flex flex-col space-y-4">
          <a href="#home" class="text-primary hover:text-accent transition-colors duration-300">首页</a>
          <a href="#about" class="text-primary hover:text-accent transition-colors duration-300">关于我们</a>
          <a href="#classes" class="text-primary hover:text-accent transition-colors duration-300">课程</a>
          <a href="#teachers" class="text-primary hover:text-accent transition-colors duration-300">导师</a>
          <a href="#pricing" class="text-primary hover:text-accent transition-colors duration-300">价格</a>
          <a href="#contact" class="bg-primary text-white px-5 py-2 rounded-full text-center hover:bg-opacity-90 transition-all duration-300">预约体验</a>
        </div>
      </div>
    </div>
  </header>

  <!-- 英雄区域 -->
  <section id="home" class="bg-hero-pattern bg-cover bg-center h-screen flex items-center">
    <div class="container mx-auto px-4 md:px-6">
      <div class="max-w-3xl text-center mx-auto">
        <h1 class="text-[clamp(2.5rem,5vw,4rem)] font-bold text-white mb-6 leading-tight text-shadow">
          开启您的<span class="text-secondary">瑜伽</span>之旅，找回内心的平静
        </h1>
        <p class="text-[clamp(1rem,2vw,1.25rem)] text-white/90 mb-8 max-w-2xl mx-auto">
          在禅心瑜伽，我们通过古老的瑜伽智慧，帮助您平衡身心，提升生活品质，发现内在的力量与美。
        </p>
        <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
          <a href="#classes" class="bg-secondary text-primary px-8 py-3 rounded-full font-medium hover:bg-opacity-80 transition-all duration-300 w-full sm:w-auto">
            探索课程
          </a>
          <a href="#contact" class="bg-transparent border-2 border-white text-white px-8 py-3 rounded-full font-medium hover:bg-white/10 transition-all duration-300 w-full sm:w-auto">
            免费咨询
          </a>
        </div>
      </div>
    </div>
    
    <!-- 向下滚动指示 -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <a href="#about" class="text-white/80 hover:text-white transition-colors duration-300">
        <i class="fa fa-angle-down text-3xl"></i>
      </a>
    </div>
  </section>

  <!-- 关于我们 -->
  <section id="about" class="py-20 bg-white">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-4">关于禅心瑜伽</h2>
        <div class="w-20 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-neutral/70 max-w-3xl mx-auto">我们致力于为您提供最纯正的瑜伽体验，帮助您在繁忙的现代生活中找到平衡与宁静。</p>
      </div>
      
      <div class="grid md:grid-cols-2 gap-12 items-center section-fade-in">
        <div>
          <img src="https://picsum.photos/id/1025/800/600" alt="瑜伽工作室环境" class="rounded-lg shadow-xl w-full h-auto object-cover">
        </div>
        
        <div class="space-y-6">
          <h3 class="text-2xl font-bold text-primary">我们的故事</h3>
          <p class="text-neutral/80">禅心瑜伽创立于2010年，由资深瑜伽导师李静女士创办。我们的愿景是通过瑜伽的练习，帮助更多人实现身心的和谐与健康。</p>
          
          <div class="grid grid-cols-2 gap-6 mt-8">
            <div class="flex flex-col items-center text-center p-4 bg-secondary/30 rounded-lg">
              <i class="fa fa-calendar-check-o text-3xl text-primary mb-3"></i>
              <h4 class="font-medium text-primary">15年+</h4>
              <p class="text-sm text-neutral/70">教学经验</p>
            </div>
            
            <div class="flex flex-col items-center text-center p-4 bg-secondary/30 rounded-lg">
              <i class="fa fa-users text-3xl text-primary mb-3"></i>
              <h4 class="font-medium text-primary">10000+</h4>
              <p class="text-sm text-neutral/70">满意学员</p>
            </div>
            
            <div class="flex flex-col items-center text-center p-4 bg-secondary/30 rounded-lg">
              <i class="fa fa-certificate text-3xl text-primary mb-3"></i>
              <h4 class="font-medium text-primary">20+</h4>
              <p class="text-sm text-neutral/70">认证导师</p>
            </div>
            
            <div class="flex flex-col items-center text-center p-4 bg-secondary/30 rounded-lg">
              <i class="fa fa-map-marker text-3xl text-primary mb-3"></i>
              <h4 class="font-medium text-primary">5</h4>
              <p class="text-sm text-neutral/70">城市分店</p>
            </div>
          </div>
          
          <a href="#contact" class="inline-block bg-primary text-white px-6 py-3 rounded-full hover:bg-opacity-90 transition-all duration-300 mt-4">
            了解更多 <i class="fa fa-arrow-right ml-2"></i>
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- 核心价值 -->
  <section class="py-20 bg-yoga-pose bg-cover bg-center bg-fixed">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-white mb-4">我们的核心价值</h2>
        <div class="w-20 h-1 bg-secondary mx-auto mb-6"></div>
        <p class="text-white/80 max-w-3xl mx-auto">这些价值观指引着我们的教学和服务，是禅心瑜伽的灵魂所在。</p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8 section-fade-in">
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-8 text-center hover:bg-white/20 transition-all duration-300">
          <i class="fa fa-heart text-4xl text-secondary mb-6"></i>
          <h3 class="text-xl font-bold text-white mb-4">身心合一</h3>
          <p class="text-white/80">我们相信瑜伽不仅仅是身体的锻炼，更是心灵的修行。通过体式、呼吸和冥想，实现身心的和谐统一。</p>
        </div>
        
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-8 text-center hover:bg-white/20 transition-all duration-300">
          <i class="fa fa-tree text-4xl text-secondary mb-6"></i>
          <h3 class="text-xl font-bold text-white mb-4">自然平衡</h3>
          <p class="text-white/80">尊重自然规律，帮助学员在生活中找到平衡。我们的课程注重整体性，不仅仅关注体式，更关注生活方式的调整。</p>
        </div>
        
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-8 text-center hover:bg-white/20 transition-all duration-300">
          <i class="fa fa-lightbulb-o text-4xl text-secondary mb-6"></i>
          <h3 class="text-xl font-bold text-white mb-4">个性化指导</h3>
          <p class="text-white/80">每个人的身体和需求都是独特的。我们的导师会根据学员的实际情况，提供个性化的指导和建议。</p>
        </div>
      </div>
    </div>
  </section>

  <!-- 课程介绍 -->
  <section id="classes" class="py-20 bg-white">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-4">精选课程</h2>
        <div class="w-20 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-neutral/70 max-w-3xl mx-auto">我们提供多种类型的瑜伽课程，无论您是初学者还是有经验的练习者，都能找到适合自己的课程。</p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8 section-fade-in">
        <!-- 哈他瑜伽 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1015/600/400" alt="哈他瑜伽课程" class="w-full h-64 object-cover">
          <div class="p-6">
            <div class="flex justify-between items-center mb-3">
              <span class="bg-primary/10 text-primary text-sm font-medium px-3 py-1 rounded-full">初学者友好</span>
              <span class="text-neutral/60 text-sm"><i class="fa fa-clock-o mr-1"></i> 60分钟</span>
            </div>
            <h3 class="text-xl font-bold text-primary mb-3">哈他瑜伽</h3>
            <p class="text-neutral/70 mb-4">哈他瑜伽是最常见的瑜伽类型，适合各年龄段和健身水平的人群。课程注重呼吸与体式的结合，帮助提高柔韧性和力量。</p>
            <div class="flex justify-between items-center">
              <span class="text-primary font-bold text-lg">¥180<span class="text-sm font-normal text-neutral/60">/节</span></span>
              <a href="#contact" class="text-primary hover:text-accent transition-colors duration-300">
                立即预约 <i class="fa fa-arrow-right ml-1"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- 流瑜伽 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1021/600/400" alt="流瑜伽课程" class="w-full h-64 object-cover">
          <div class="p-6">
            <div class="flex justify-between items-center mb-3">
              <span class="bg-accent/10 text-accent text-sm font-medium px-3 py-1 rounded-full">中级</span>
              <span class="text-neutral/60 text-sm"><i class="fa fa-clock-o mr-1"></i> 75分钟</span>
            </div>
            <h3 class="text-xl font-bold text-primary mb-3">流瑜伽</h3>
            <p class="text-neutral/70 mb-4">流瑜伽是一种动态的瑜伽形式，强调体式之间的流畅过渡。通过连续的动作和深呼吸，提高心肺功能和身体协调性。</p>
            <div class="flex justify-between items-center">
              <span class="text-primary font-bold text-lg">¥200<span class="text-sm font-normal text-neutral/60">/节</span></span>
              <a href="#contact" class="text-primary hover:text-accent transition-colors duration-300">
                立即预约 <i class="fa fa-arrow-right ml-1"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- 冥想课程 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1023/600/400" alt="冥想课程" class="w-full h-64 object-cover">
          <div class="p-6">
            <div class="flex justify-between items-center mb-3">
              <span class="bg-secondary/30 text-primary text-sm font-medium px-3 py-1 rounded-full">所有级别</span>
              <span class="text-neutral/60 text-sm"><i class="fa fa-clock-o mr-1"></i> 45分钟</span>
            </div>
            <h3 class="text-xl font-bold text-primary mb-3">冥想课程</h3>
            <p class="text-neutral/70 mb-4">冥想是瑜伽的重要组成部分。本课程将引导您通过呼吸和专注技巧，减轻压力，提高专注力，培养内心的平静。</p>
            <div class="flex justify-between items-center">
              <span class="text-primary font-bold text-lg">¥150<span class="text-sm font-normal text-neutral/60">/节</span></span>
              <a href="#contact" class="text-primary hover:text-accent transition-colors duration-300">
                立即预约 <i class="fa fa-arrow-right ml-1"></i>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="text-center mt-12 section-fade-in">
        <a href="#contact" class="inline-block bg-primary text-white px-8 py-3 rounded-full hover:bg-opacity-90 transition-all duration-300">
          查看全部课程 <i class="fa fa-chevron-right ml-2"></i>
        </a>
      </div>
    </div>
  </section>

  <!-- 导师团队 -->
  <section id="teachers" class="py-20 bg-secondary/20">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-4">专业导师团队</h2>
        <div class="w-20 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-neutral/70 max-w-3xl mx-auto">我们的导师都拥有丰富的教学经验和专业认证，致力于为您提供最优质的瑜伽指导。</p>
      </div>
      
      <div class="grid md:grid-cols-4 gap-8 section-fade-in">
        <!-- 导师1 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1000/600/800" alt="李静导师" class="w-full h-80 object-cover object-center">
          <div class="p-6 text-center">
            <h3 class="text-xl font-bold text-primary mb-1">李静</h3>
            <p class="text-accent mb-3">创始人 & 资深导师</p>
            <p class="text-neutral/70 text-sm mb-4">国际瑜伽联盟认证导师，拥有15年教学经验，专注于哈他瑜伽和冥想教学。</p>
            <div class="flex justify-center space-x-3">
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-instagram"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-facebook"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-linkedin"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- 导师2 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1001/600/800" alt="王明导师" class="w-full h-80 object-cover object-center">
          <div class="p-6 text-center">
            <h3 class="text-xl font-bold text-primary mb-1">王明</h3>
            <p class="text-accent mb-3">流瑜伽专家</p>
            <p class="text-neutral/70 text-sm mb-4">RYT-500认证导师，曾在印度进修3年，擅长流瑜伽和阿斯汤加瑜伽教学。</p>
            <div class="flex justify-center space-x-3">
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-instagram"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-facebook"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-linkedin"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- 导师3 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1005/600/800" alt="张丽导师" class="w-full h-80 object-cover object-center">
          <div class="p-6 text-center">
            <h3 class="text-xl font-bold text-primary mb-1">张丽</h3>
            <p class="text-accent mb-3">阴瑜伽导师</p>
            <p class="text-neutral/70 text-sm mb-4">专注于阴瑜伽和恢复性瑜伽教学，帮助学员缓解压力，恢复身体能量。</p>
            <div class="flex justify-center space-x-3">
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-instagram"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-facebook"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-linkedin"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- 导师4 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <img src="https://picsum.photos/id/1006/600/800" alt="李强导师" class="w-full h-80 object-cover object-center">
          <div class="p-6 text-center">
            <h3 class="text-xl font-bold text-primary mb-1">李强</h3>
            <p class="text-accent mb-3">冥想与呼吸专家</p>
            <p class="text-neutral/70 text-sm mb-4">心理学背景，结合科学与传统，教授实用的冥想技巧和呼吸方法。</p>
            <div class="flex justify-center space-x-3">
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-instagram"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-facebook"></i>
              </a>
              <a href="#" class="text-neutral/50 hover:text-primary transition-colors duration-300">
                <i class="fa fa-linkedin"></i>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 课程时间表 -->
  <section class="py-20 bg-white">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-4">课程时间表</h2>
        <div class="w-20 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-neutral/70 max-w-3xl mx-auto">查看我们的课程时间表，选择适合您的课程和时间。我们每周更新课程安排，确保提供丰富多样的选择。</p>
      </div>
      
      <div class="bg-white rounded-xl shadow-lg overflow-hidden section-fade-in">
        <div class="overflow-x-auto">
          <table class="w-full">
            <thead>
              <tr class="bg-primary text-white">
                <th class="py-4 px-6 text-left">时间</th>
                <th class="py-4 px-6 text-left">周一</th>
                <th class="py-4 px-6 text-left">周二</th>
                <th class="py-4 px-6 text-left">周三</th>
                <th class="py-4 px-6 text-left">周四</th>
                <th class="py-4 px-6 text-left">周五</th>
                <th class="py-4 px-6 text-left">周六</th>
                <th class="py-4 px-6 text-left">周日</th>
              </tr>
            </thead>
            <tbody>
              <tr class="border-b border-gray-200">
                <td class="py-4 px-6 font-medium">07:00 - 08:00</td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">李静</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">流瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">王明</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">冥想</span>
                  <div class="text-xs text-neutral/60 mt-1">李强</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">流瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">王明</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">李静</div>
                </td>
                <td class="py-4 px-6"></td>
              </tr>
              <tr class="border-b border-gray-200">
                <td class="py-4 px-6 font-medium">12:00 - 13:00</td>
                <td class="py-4 px-6">
                  <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">阴瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">冥想</span>
                  <div class="text-xs text-neutral/60 mt-1">李强</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">阴瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">流瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">王明</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">冥想</span>
                  <div class="text-xs text-neutral/60 mt-1">李强</div>
                </td>
                <td class="py-4 px-6"></td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">李静</div>
                </td>
              </tr>
              <tr class="border-b border-gray-200">
                <td class="py-4 px-6 font-medium">18:00 - 19:30</td>
                <td class="py-4 px-6">
                  <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">流瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">王明</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">李静</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">冥想</span>
                  <div class="text-xs text-neutral/60 mt-1">李强</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">阴瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">流瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">王明</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">李静</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">阴瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
              </tr>
              <tr>
                <td class="py-4 px-6 font-medium">19:45 - 21:00</td>
                <td class="py-4 px-6">
                  <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">冥想</span>
                  <div class="text-xs text-neutral/60 mt-1">李强</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">阴瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">流瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">王明</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">哈他瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">李静</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">冥想</span>
                  <div class="text-xs text-neutral/60 mt-1">李强</div>
                </td>
                <td class="py-4 px-6">
                  <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">阴瑜伽</span>
                  <div class="text-xs text-neutral/60 mt-1">张丽</div>
                </td>
                <td class="py-4 px-6"></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
      
      <div class="mt-10 text-center section-fade-in">
        <p class="text-neutral/70 mb-6">课程时间表每周更新，如需最新安排，请联系我们或查看官方APP。</p>
        <a href="#contact" class="inline-block bg-primary text-white px-8 py-3 rounded-full hover:bg-opacity-90 transition-all duration-300">
          预约课程 <i class="fa fa-calendar-plus-o ml-2"></i>
        </a>
      </div>
    </div>
  </section>

  <!-- 会员价格 -->
  <section id="pricing" class="py-20 bg-secondary/20">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-4">会员价格</h2>
        <div class="w-20 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-neutral/70 max-w-3xl mx-auto">选择适合您的会员方案，开启健康的瑜伽之旅。我们提供多种灵活的选择，满足不同需求和预算。</p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8 section-fade-in">
        <!-- 单次体验 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <div class="p-8 text-center">
            <h3 class="text-xl font-bold text-primary mb-2">单次体验</h3>
            <p class="text-neutral/60 mb-6">适合初次尝试瑜伽的新手</p>
            <div class="mb-6">
              <span class="text-4xl font-bold text-primary">¥180</span>
              <span class="text-neutral/60">/次</span>
            </div>
            <ul class="space-y-3 mb-8 text-left">
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>任选一节常规课程</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>提供瑜伽垫和基础装备</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>免费淋浴设施</span>
              </li>
              <li class="flex items-start opacity-50">
                <i class="fa fa-times text-red-500 mt-1 mr-2"></i>
                <span>无个人专属储物柜</span>
              </li>
              <li class="flex items-start opacity-50">
                <i class="fa fa-times text-red-500 mt-1 mr-2"></i>
                <span>不包含私教课程</span>
              </li>
            </ul>
            <a href="#contact" class="block w-full bg-primary text-white py-3 rounded-full hover:bg-opacity-90 transition-all duration-300">
              立即体验
            </a>
          </div>
        </div>
        
        <!-- 月度会员 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover transform md:-translate-y-4 border-2 border-primary relative">
          <div class="absolute top-0 right-0 bg-primary text-white text-xs font-bold px-4 py-1 rounded-bl-lg">
            最受欢迎
          </div>
          <div class="p-8 text-center">
            <h3 class="text-xl font-bold text-primary mb-2">月度会员</h3>
            <p class="text-neutral/60 mb-6">适合定期练习的爱好者</p>
            <div class="mb-6">
              <span class="text-4xl font-bold text-primary">¥1280</span>
              <span class="text-neutral/60">/月</span>
            </div>
            <ul class="space-y-3 mb-8 text-left">
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>无限次参加常规课程</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>提供瑜伽垫和基础装备</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>免费淋浴设施</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>个人专属储物柜</span>
              </li>
              <li class="flex items-start opacity-50">
                <i class="fa fa-times text-red-500 mt-1 mr-2"></i>
                <span>包含2节私教课程</span>
              </li>
            </ul>
            <a href="#contact" class="block w-full bg-primary text-white py-3 rounded-full hover:bg-opacity-90 transition-all duration-300">
              立即加入
            </a>
          </div>
        </div>
        
        <!-- 年度会员 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden scale-up-hover">
          <div class="p-8 text-center">
            <h3 class="text-xl font-bold text-primary mb-2">年度会员</h3>
            <p class="text-neutral/60 mb-6">适合长期坚持的瑜伽修行者</p>
            <div class="mb-6">
              <span class="text-4xl font-bold text-primary">¥9800</span>
              <span class="text-neutral/60">/年</span>
            </div>
            <ul class="space-y-3 mb-8 text-left">
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>无限次参加所有课程</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>高级瑜伽装备免费使用</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>免费淋浴和桑拿设施</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>个人专属储物柜</span>
              </li>
              <li class="flex items-start">
                <i class="fa fa-check text-green-500 mt-1 mr-2"></i>
                <span>包含12节私教课程</span>
              </li>
            </ul>
            <a href="#contact" class="block w-full bg-primary text-white py-3 rounded-full hover:bg-opacity-90 transition-all duration-300">
              立即加入
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 客户评价 -->
  <section class="py-20 bg-white">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16 section-fade-in">
        <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-4">客户评价</h2>
        <div class="w-20 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-neutral/70 max-w-3xl mx-auto">听听我们的学员怎么说，他们的真实体验和反馈是我们不断进步的动力。</p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8 section-fade-in">
        <!-- 评价1 -->
        <div class="bg-secondary/10 rounded-xl p-8 relative scale-up-hover">
          <div class="text-primary/20 text-6xl absolute -top-4 left-4">"</div>
          <div class="text-neutral/80 mb-6 relative z-10">
            加入禅心瑜伽已经三个月了，身体和精神状态都有了明显的改善。李静老师的哈他课程非常适合初学者，讲解细致，动作指导到位。环境也很舒适，是个放松身心的好地方。
          </div>
          <div class="flex items-center">
            <img src="https://picsum.photos/id/1003/100/100" alt="张女士" class="w-12 h-12 rounded-full object-cover mr-4">
            <div>
              <h4 class="font-medium text-primary">张女士</h4>
              <div class="flex text-yellow-400 text-sm">
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
              </div>
            </div>
          </div>
        </div>
        
        <!-- 评价2 -->
        <div class="bg-secondary/10 rounded-xl p-8 relative scale-up-hover">
          <div class="text-primary/20 text-6xl absolute -top-4 left-4">"</div>
          <div class="text-neutral/80 mb-6 relative z-10">
            王明老师的流瑜伽课程充满活力，每次上完都感觉身心舒畅。作为一名办公室工作者，长期的久坐导致腰背疼痛，通过瑜伽练习，这些问题得到了明显缓解。非常推荐给所有需要放松和锻炼的朋友！
          </div>
          <div class="flex items-center">
            <img src="https://picsum.photos/id/1012/100/100" alt="李先生" class="w-12 h-12 rounded-full object-cover mr-4">
            <div>
              <h4 class="font-medium text-primary">李先生</h4>
              <div class="flex text-yellow-400 text-sm">
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star-half-o"></i>
              </div>
            </div>
          </div>
        </div>
        
        <!-- 评价3 -->
        <div class="bg-secondary/10 rounded-xl p-8 relative scale-up-hover">
          <div class="text-primary/20 text-6xl absolute -top-4 left-4">"</div>
          <div class="text-neutral/80 mb-6 relative z-10">
            李强老师的冥想课程帮助我在繁忙的生活中找到了内心的平静。每天早上参加冥想，让我一整天都精力充沛，专注力更强。禅心瑜伽的环境安静舒适，是城市中难得的一片净土。
          </div>
          <div class="flex items-center">
            <img src="https://picsum.photos/id/1027/100/100" alt="王女士" class="w-12 h-12 rounded-full object-cover mr-4">
            <div>
              <h4 class="font-medium text-primary">王女士</h4>
              <div class="flex text-yellow-400 text-sm">
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
                <i class="fa fa-star"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 联系我们 -->
  <section id="contact" class="py-20 bg-primary/5">
    <div class="container mx-auto px-4 md:px-6">
      <div class="grid md:grid-cols-2 gap-12 items-center section-fade-in">
        <div>
          <h2 class="text-[clamp(1.5rem,3vw,2.5rem)] font-bold text-primary mb-6">联系我们</h2>
          <p class="text-neutral/70 mb-8">无论您有任何问题或需要了解更多信息，都可以通过以下方式联系我们。我们期待您的咨询，将竭诚为您服务。</p>
          
          <div class="space-y-6 mb-8">
            <div class="flex items-start">
              <div class="bg-primary/10 p-3 rounded-full mr-4">
                <i class="fa fa-map-marker text-primary"></i>
              </div>
              <div>
                <h4 class="font-medium text-primary mb-1">地址</h4>
                <p class="text-neutral/70">北京市朝阳区建国路88号现代城SOHO B座1502室</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="bg-primary/10 p-3 rounded-full mr-4">
                <i class="fa fa-phone text-primary"></i>
              </div>
              <div>
                <h4 class="font-medium text-primary mb-1">电话</h4>
                <p class="text-neutral/70">+86 10 8888 7777</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="bg-primary/10 p-3 rounded-full mr-4">
                <i class="fa fa-envelope text-primary"></i>
              </div>
              <div>
                <h4 class="font-medium text-primary mb-1">邮箱</h4>
                <p class="text-neutral/70">info@chanxinyoga.com</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="bg-primary/10 p-3 rounded-full mr-4">
                <i class="fa fa-clock-o text-primary"></i>
              </div>
              <div>
                <h4 class="font-medium text-primary mb-1">营业时间</h4>
                <p class="text-neutral/70">周一至周五: 06:30 - 22:00</p>
                <p class="text-neutral/70">周六至周日: 07:30 - 20:00</p>
              </div>
            </div>
          </div>
          
          <div class="flex space-x-4">
            <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary w-10 h-10 rounded-full flex items-center justify-center transition-all duration-300">
              <i class="fa fa-weixin"></i>
            </a>
            <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary w-10 h-10 rounded-full flex items-center justify-center transition-all duration-300">
              <i class="fa fa-weibo"></i>
            </a>
            <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary w-10 h-10 rounded-full flex items-center justify-center transition-all duration-300">
              <i class="fa fa-instagram"></i>
            </a>
            <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary w-10 h-10 rounded-full flex items-center justify-center transition-all duration-300">
              <i class="fa fa-youtube-play"></i>
            </a>
          </div>
        </div>
        
        <div class="bg-white rounded-xl shadow-lg p-8">
          <h3 class="text-xl font-bold text-primary mb-6">预约体验课程</h3>
          <form id="contact-form" class="space-y-6">
            <div>
              <label for="name" class="block text-sm font-medium text-neutral mb-2">姓名</label>
              <input type="text" id="name" name="name" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-all duration-300" placeholder="请输入您的姓名" required>
            </div>
            
            <div>
              <label for="phone" class="block text-sm font-medium text-neutral mb-2">电话</label>
              <input type="tel" id="phone" name="phone" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-all duration-300" placeholder="请输入您的电话号码" required>
            </div>
            
            <div>
              <label for="email" class="block text-sm font-medium text-neutral mb-2">邮箱</label>
              <input type="email" id="email" name="email" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-all duration-300" placeholder="请输入您的邮箱地址" required>
            </div>
            
            <div>
              <label for="course" class="block text-sm font-medium text-neutral mb-2">感兴趣的课程</label>
              <select id="course" name="course" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-all duration-300" required>
                <option value="" disabled selected>请选择课程</option>
                <option value="hatha">哈他瑜伽</option>
                <option value="vinyasa">流瑜伽</option>
                <option value="yin">阴瑜伽</option>
                <option value="meditation">冥想课程</option>
                <option value="other">其他课程</option>
              </select>
            </div>
            
            <div>
              <label for="message" class="block text-sm font-medium text-neutral mb-2">留言</label>
              <textarea id="message" name="message" rows="4" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-all duration-300" placeholder="有什么想告诉我们的？"></textarea>
            </div>
            
            <button type="submit" class="w-full bg-primary text-white py-3 rounded-lg hover:bg-opacity-90 transition-all duration-300">
              提交预约 <i class="fa fa-paper-plane ml-2"></i>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>

  <!-- 地图 -->
  <div class="h-96 w-full bg-gray-200 relative">
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3053.977000721237!2d116.4810282153257!3d39.92250919412757!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x35f1ad759f90a02f%3A0x3a91d66e52f9c09a!2sSOHO%20Modern%20City!5e0!3m2!1sen!2sus!4v1626345033177!5m2!1sen!2sus" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
  </div>

  <!-- 页脚 -->
  <footer class="bg-neutral text-white py-12">
    <div class="container mx-auto px-4 md:px-6">
      <div class="grid md:grid-cols-4 gap-8">
        <div>
          <div class="flex items-center space-x-2 mb-6">
            <i class="fa fa-leaf text-2xl text-secondary"></i>
            <span class="text-xl font-serif font-bold">禅心瑜伽</span>
          </div>
          <p class="text-white/70 mb-6">禅心瑜伽致力于为您提供最纯正的瑜伽体验，帮助您在繁忙的现代生活中找到平衡与宁静。</p>
          <div class="flex space-x-4">
            <a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">
              <i class="fa fa-weixin"></i>
            </a>
            <a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">
              <i class="fa fa-weibo"></i>
            </a>
            <a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">
              <i class="fa fa-instagram"></i>
            </a>
            <a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">
              <i class="fa fa-youtube-play"></i>
            </a>
          </div>
        </div>
        
        <div>
          <h4 class="text-lg font-medium mb-6">快速链接</h4>
          <ul class="space-y-3">
            <li><a href="#home" class="text-white/70 hover:text-secondary transition-colors duration-300">首页</a></li>
            <li><a href="#about" class="text-white/70 hover:text-secondary transition-colors duration-300">关于我们</a></li>
            <li><a href="#classes" class="text-white/70 hover:text-secondary transition-colors duration-300">课程</a></li>
            <li><a href="#teachers" class="text-white/70 hover:text-secondary transition-colors duration-300">导师</a></li>
            <li><a href="#pricing" class="text-white/70 hover:text-secondary transition-colors duration-300">价格</a></li>
            <li><a href="#contact" class="text-white/70 hover:text-secondary transition-colors duration-300">联系我们</a></li>
          </ul>
        </div>
        
        <div>
          <h4 class="text-lg font-medium mb-6">课程分类</h4>
          <ul class="space-y-3">
            <li><a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">哈他瑜伽</a></li>
            <li><a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">流瑜伽</a></li>
            <li><a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">阴瑜伽</a></li>
            <li><a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">冥想课程</a></li>
            <li><a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">孕妇瑜伽</a></li>
            <li><a href="#" class="text-white/70 hover:text-secondary transition-colors duration-300">儿童瑜伽</a></li>
          </ul>
        </div>
        
        <div>
          <h4 class="text-lg font-medium mb-6">联系方式</h4>
          <ul class="space-y-3">
            <li class="flex items-start">
              <i class="fa fa-map-marker mt-1 mr-3 text-secondary"></i>
              <span class="text-white/70">北京市朝阳区建国路88号现代城SOHO B座1502室</span>
            </li>
            <li class="flex items-start">
              <i class="fa fa-phone mt-1 mr-3 text-secondary"></i>
              <span class="text-white/70">+86 10 8888 7777</span>
            </li>
            <li class="flex items-start">
              <i class="fa fa-envelope mt-1 mr-3 text-secondary"></i>
              <span class="text-white/70">info@chanxinyoga.com</span>
            </li>
            <li class="flex items-start">
              <i class="fa fa-clock-o mt-1 mr-3 text-secondary"></i>
              <span class="text-white/70">周一至周五: 06:30 - 22:00</span>
            </li>
            <li class="flex items-start">
              <i class="fa fa-clock-o mt-1 mr-3 text-secondary"></i>
              <span class="text-white/70">周六至周日: 07:30 - 20:00</span>
            </li>
          </ul>
        </div>
      </div>
      
      <div class="border-t border-white/10 mt-12 pt-8 flex flex-col md:flex-row justify-between items-center">
        <p class="text-white/70 text-sm mb-4 md:mb-0">© 2025 禅心瑜伽. 保留所有权利.</p>
        <div class="flex space-x-6">
          <a href="#" class="text-white/70 hover:text-secondary text-sm transition-colors duration-300">隐私政策</a>
          <a href="#" class="text-white/70 hover:text-secondary text-sm transition-colors duration-300">服务条款</a>
          <a href="#" class="text-white/70 hover:text-secondary text-sm transition-colors duration-300">Cookie政策</a>
        </div>
      </div>
    </div>
  </footer>

  <!-- 返回顶部按钮 -->
  <button id="back-to-top" class="fixed bottom-6 right-6 bg-primary text-white w-12 h-12 rounded-full flex items-center justify-center shadow-lg opacity-0 invisible transition-all duration-300 z-50">
    <i class="fa fa-chevron-up"></i>
  </button>

  <!-- JavaScript -->
  <script>
    // 导航栏滚动效果
    const navbar = document.getElementById('navbar');
    const backToTop = document.getElementById('back-to-top');
    
    window.addEventListener('scroll', function() {
      if (window.scrollY > 50) {
        navbar.classList.add('nav-scrolled');
        backToTop.classList.remove('opacity-0', 'invisible');
        backToTop.classList.add('opacity-100', 'visible');
      } else {
        navbar.classList.remove('nav-scrolled');
        backToTop.classList.add('opacity-0', 'invisible');
        backToTop.classList.remove('opacity-100', 'visible');
      }
      
      // 滚动时的淡入效果
      const fadeElements = document.querySelectorAll('.section-fade-in');
      fadeElements.forEach(element => {
        const elementTop = element.getBoundingClientRect().top;
        const windowHeight = window.innerHeight;
        
        if (elementTop < windowHeight * 0.85) {
          element.classList.add('visible');
        }
      });
    });
    
    // 移动端菜单切换
    const menuToggle = document.getElementById('menu-toggle');
    const mobileMenu = document.getElementById('mobile-menu');
    
    menuToggle.addEventListener('click', function() {
      mobileMenu.classList.toggle('hidden');
      
      // 切换图标
      const icon = menuToggle.querySelector('i');
      if (icon.classList.contains('fa-bars')) {
        icon.classList.remove('fa-bars');
        icon.classList.add('fa-times');
      } else {
        icon.classList.remove('fa-times');
        icon.classList.add('fa-bars');
      }
    });
    
    // 平滑滚动
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        
        // 关闭移动菜单
        if (!mobileMenu.classList.contains('hidden')) {
          mobileMenu.classList.add('hidden');
          const icon = menuToggle.querySelector('i');
          icon.classList.remove('fa-times');
          icon.classList.add('fa-bars');
        }
        
        const targetId = this.getAttribute('href');
        const targetElement = document.querySelector(targetId);
        
        if (targetElement) {
          window.scrollTo({
            top: targetElement.offsetTop - 80,
            behavior: 'smooth'
          });
        }
      });
    });
    
    // 返回顶部
    backToTop.addEventListener('click', function() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    });
    
    // 表单提交
    const contactForm = document.getElementById('contact-form');
    
    contactForm.addEventListener('submit', function(e) {
      e.preventDefault();
      
      // 这里可以添加表单验证和提交逻辑
      alert('预约已提交，我们将尽快与您联系！');
      contactForm.reset();
    });
  </script>
</body>
</html>
    
