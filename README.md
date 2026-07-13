<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مطعم قيس - القائمة الرسمية</title>
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #dc2626; /* أحمر دافئ */
            --secondary: #eab308; /* أصفر ذهبي */
            --dark: #1e1b4b;
            --light: #fffdfa;
            --gray: #64748b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--light);
            color: #334155;
        }

        /* الهيدر والقائمة العلوية */
        header {
            background-color: #ffffff;
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 10px 20px;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo-area {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-placeholder {
            width: 55px;
            height: 55px;
            background-color: #111;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px solid var(--secondary);
            color: #fff;
            font-size: 24px;
        }

        .logo-text h1 {
            font-size: 20px;
            color: var(--primary);
            font-weight: 900;
        }
        .logo-text p {
            font-size: 11px;
            color: var(--gray);
            letter-spacing: 1px;
        }

        .contact-btn {
            background-color: var(--primary);
            color: white;
            padding: 8px 16px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            transition: 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .contact-btn:hover {
            background-color: #b91c1c;
            transform: translateY(-2px);
        }

        /* البانر الترحيبي مع صورة خلفية أكل منوعة */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.55), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1504674900247-0877df9cc836?q=80&w=1970&auto=format&fit=crop') center/cover;
            height: 350px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            padding: 20px;
        }

        .hero h2 {
            font-size: 36px;
            font-weight: 900;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .hero p {
            font-size: 18px;
            color: var(--secondary);
            margin-bottom: 20px;
            font-weight: 600;
        }

        /* التبويبات للتنقل بين الأصناف */
        .tabs-container {
            position: sticky;
            top: 75px;
            background: #ffffff;
            padding: 15px 0;
            box-shadow: 0 4px 6px -4px rgba(0,0,0,0.1);
            z-index: 90;
            overflow-x: auto;
            white-space: nowrap;
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .tab-button {
            background: #f1f5f9;
            border: none;
            padding: 10px 24px;
            border-radius: 50px;
            font-size: 15px;
            font-weight: 700;
            cursor: pointer;
            color: #475569;
            transition: 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .tab-button.active, .tab-button:hover {
            background-color: var(--secondary);
            color: #000;
        }

        /* قسم المنيو وقائمة الطعام */
        .menu-section {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        .category-title {
            font-size: 24px;
            color: var(--dark);
            margin-bottom: 25px;
            border-right: 5px solid var(--primary);
            padding-right: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }

        .menu-item {
            background: white;
            border-radius: 16px;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05);
            overflow: hidden;
            border: 1px solid #f1f5f9;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: 0.3s;
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }

        .item-image {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .item-content {
            padding: 20px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .item-info h3 {
            font-size: 18px;
            color: #1e293b;
            margin-bottom: 8px;
        }

        .item-desc {
            font-size: 13px;
            color: var(--gray);
            margin-bottom: 15px;
            line-height: 1.6;
        }

        /* خيارات التبديل بين الدجاج واللحم */
        .type-selector {
            display: flex;
            background: #f8fafc;
            border-radius: 8px;
            padding: 4px;
            margin-bottom: 15px;
            gap: 4px;
        }

        .type-btn {
            flex: 1;
            border: none;
            background: transparent;
            padding: 6px;
            font-size: 12px;
            font-weight: 700;
            border-radius: 6px;
            cursor: pointer;
            color: #64748b;
            transition: 0.2s;
        }

        .type-btn.active {
            background: white;
            color: var(--primary);
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }

        .item-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: auto;
            border-top: 1px dashed #e2e8f0;
            padding-top: 15px;
        }

        .price-tag {
            font-size: 20px;
            font-weight: 800;
            color: var(--primary);
        }

        .price-tag span {
            font-size: 12px;
            font-weight: 400;
            color: var(--gray);
            margin-right: 4px;
        }

        /* فوتر الصفحة وأزرار التواصل */
        footer {
            background-color: #111827;
            color: #f3f4f6;
            padding: 40px 20px;
            text-align: center;
            margin-top: 60px;
        }

        .footer-socials {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }

        .social-icon {
            width: 45px;
            height: 45px;
            background-color: #1f2937;
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            text-decoration: none;
            transition: 0.3s;
        }

        .social-icon.fb:hover { background-color: #1877f2; }
        .social-icon.ph:hover { background-color: #10b981; }

        .footer-text {
            font-size: 13px;
            color: #9ca3af;
        }

        /* شاشات الموبايل */
        @media (max-width: 600px) {
            .tabs-container {
                justify-content: flex-start;
                padding: 15px;
            }
            .hero h2 {
                font-size: 28px;
            }
            .menu-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- الهيدر العلوي -->
    <header>
        <div class="nav-container">
            <div class="logo-area">
                <div class="logo-placeholder">
                    <i class="fa-solid fa-utensils" style="color: var(--secondary);"></i>
                </div>
                <div class="logo-text">
                    <h1>مطعم قيس</h1>
                    <p>FOUNDED 2010</p>
                </div>
            </div>
            <!-- زر الاتصال المباشر بالرقم -->
            <a href="tel:0924936169" class="contact-btn">
                <i class="fa-solid fa-phone"></i>
                <span>اتصل الآن</span>
            </a>
        </div>
    </header>

    <!-- البانر الترحيبي -->
    <section class="hero">
        <h2>مطعم قيس للوجبات السريعة</h2>
        <p>تذوق طعم الجودة والخبرة منذ عام 2010</p>
    </section>

    <!-- أزرار التصفح السريع -->
    <div class="tabs-container">
        <button class="tab-button active" onclick="filterMenu('all')"><i class="fa-solid fa-border-all"></i> الكل</button>
        <button class="tab-button" onclick="filterMenu('meals')"><i class="fa-solid fa-burger"></i> الوجبات والسندوتشات</button>
        <button class="tab-button" onclick="filterMenu('pizza')"><i class="fa-solid fa-pizza-slice"></i> البيتزا</button>
    </div>

    <!-- المنيو الرئيسي -->
    <main class="menu-section">
        
        <!-- قسم الوجبات والسندوتشات -->
        <div class="menu-cate-wrapper" id="cat-meals">
            <h2 class="category-title"><i class="fa-solid fa-burger" style="color: var(--primary);"></i> الوجبات والسندوتشات</h2>
            <div class="menu-grid">
                
                <!-- طابونة -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1626082927389-6cd097cdc6ec?q=80&w=500&auto=format&fit=crop" alt="طابونة" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>طابونة</h3>
                            <p class="item-desc">خبزة طابونة ساخنة ومقرمشة مع الحشوة المفضلة لديك.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 12)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 14)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">12</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- برجر -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?q=80&w=500&auto=format&fit=crop" alt="برجر" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>برجر</h3>
                            <p class="item-desc">برجر شهي ومحضر بخلطتنا الخاصة يقدم ساخناً.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 9)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 10)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">9</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- مقلوب -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1598182126876-04cbe48792cc?q=80&w=500&auto=format&fit=crop" alt="مقلوب" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>مقلوب</h3>
                            <p class="item-desc">المقلوب التونسي المميز بالجبنة الغنية والحشوات الرائعة.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 18)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 20)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">18</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- باقيت -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1509722747041-616f39b57569?q=80&w=500&auto=format&fit=crop" alt="باقيت" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>باقيت</h3>
                            <p class="item-desc">سندوتش باقيت فرنسي طويل غني بالنكهة اللذيذة.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 22)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 25)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">22</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- تشيز -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1528698827591-e19ccd7bc23d?q=80&w=500&auto=format&fit=crop" alt="تشيز" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>تشيز</h3>
                            <p class="item-desc">عشاق الأجبان! سندوتش غارق بصلصة الجبنة الذائبة المميزة.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 25)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 27)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">25</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- مشتعلة -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1606755962773-d324e0a13086?q=80&w=500&auto=format&fit=crop" alt="مشتعلة" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>سندوتش المشتعلة 🔥</h3>
                            <p class="item-desc">سندوتش حار لعشاق المذاق الحار والمليء بالتوابل القوية.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 25)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 27)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">25</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- كورنو -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1608039829572-78524f79c4c7?q=80&w=500&auto=format&fit=crop" alt="كورنو" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>كورنو</h3>
                            <p class="item-desc">لفائف الكورنو الهشة والشهية المجهزة بحشوة مميزة.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 22)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 25)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">22</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- ليباني -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1541518763669-27fef04b14ea?q=80&w=500&auto=format&fit=crop" alt="ليباني" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>ليباني</h3>
                            <p class="item-desc">سندوتش على الطريقة اللبنانية الكلاسيكية الخفيفة والشهية.</p>
                            <div class="type-selector">
                                <button class="type-btn active" onclick="updatePrice(this, 22)">دجاج</button>
                                <button class="type-btn" onclick="updatePrice(this, 25)">لحم</button>
                            </div>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span class="price-val">22</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- وجبة رز -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1512058564366-18510be2db19?q=80&w=500&auto=format&fit=crop" alt="وجبة رز" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>وجبة رز</h3>
                            <p class="item-desc">طبق أرز فاخر يقدم مع الخلطة والتوابل الرائعة للمطعم.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>20</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

            </div>
        </div>

        <!-- قسم البيتزا -->
        <div class="menu-cate-wrapper" id="cat-pizza">
            <h2 class="category-title"><i class="fa-solid fa-pizza-slice" style="color: var(--primary);"></i> بيتزا الفرن المميزة</h2>
            <div class="menu-grid">
                
                <!-- بيتزا جبنه -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1513104890138-7c749659a591?q=80&w=500&auto=format&fit=crop" alt="بيتزا جبنة" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا جبنة</h3>
                            <p class="item-desc">صلصة طماطم غنية مغطاة بطبقة كثيفة من جبن الموزاريلا الفاخر.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>14</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- بيتزا خضرة -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1571407970349-bc81e7e96d47?q=80&w=500&auto=format&fit=crop" alt="بيتزا خضار" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا خضار</h3>
                            <p class="item-desc">مزيج من الفلفل الأخضر، الزيتون، الطماطم والبصل الطازج.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>15</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- بيتزافقاع -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1604917869287-3ae73c77e227?q=80&w=500&auto=format&fit=crop" alt="بيتزا فقع" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا فقع (مشروم)</h3>
                            <p class="item-desc">قطع المشروم الطازجة مع صلصة البيتزا والجبنة الذائبة.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>17</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- تن -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1593560708920-61dd98c46a4e?q=80&w=500&auto=format&fit=crop" alt="بيتزا تن" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا تن</h3>
                            <p class="item-desc">بيتزا التونة الكلاسيكية واللذيذة بنكهة غنية ومميزة.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>18</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- بيتزا دجاج -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?q=80&w=500&auto=format&fit=crop" alt="بيتزا دجاج" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا دجاج</h3>
                            <p class="item-desc">قطع الدجاج المتبلة والمشوية بعناية فوق طبقة الجبن الشهية.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>22</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- بيتزا مشكلة تن فقاع -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1534308983496-4fabb1a015ee?q=80&w=500&auto=format&fit=crop" alt="بيتزا مشكلة" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا مشكلة (تن + فقع)</h3>
                            <p class="item-desc">مزيج مميز ورائع يجمع بين التونة وقطع الفقع اللذيذة.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>22</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- بيتزا مشكلة تامة -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1628840042765-356cda07504e?q=80&w=500&auto=format&fit=crop" alt="بيتزا تامة" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا مشكلة تامة</h3>
                            <p class="item-desc">تجمع كل المكونات الفاخرة في بيتزا واحدة لتجربة لا تقاوم.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>25</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

                <!-- بيتزا دبل -->
                <div class="menu-item">
                    <img src="https://images.unsplash.com/photo-1594007654729-407ededc496a?q=80&w=500&auto=format&fit=crop" alt="بيتزا دبل" class="item-image">
                    <div class="item-content">
                        <div class="item-info">
                            <h3>بيتزا دبل</h3>
                            <p class="item-desc">ضعف الجبنة وضعف الحشوة لعشاق الأحجام الكبيرة والوجبات المشبعة.</p>
                        </div>
                        <div class="item-footer">
                            <div class="price-tag"><span>30</span><span>د.ل</span></div>
                        </div>
                    </div>
                </div>

            </div>
        </div>

    </main>

    <!-- الفوتر ومعلومات التواصل -->
    <footer>
        <h3 style="color: var(--secondary); font-size: 22px; margin-bottom: 10px;">مطعم قيس</h3>
        <p>جودة وطعم يستحق ثقتكم منذ 2010</p>
        
        <div class="footer-socials">
            <a href="https://www.facebook.com/share/1DAfhrBwak/?mibextid=wwXIfr" target="_blank" class="social-icon fb">
                <i class="fa-brands fa-facebook-f"></i>
            </a>
            <a href="tel:0924936169" class="social-icon ph">
                <i class="fa-solid fa-phone"></i>
            </a>
        </div>

        <p class="footer-text">رقم الهاتف للدعم والطلب: 0924936169</p>
        <p class="footer-text" style="margin-top: 15px; font-size: 11px;">© 2026 مطعم قيس. جميع الحقوق محفوظة.</p>
    </footer>

    <!-- أكواد الـ JavaScript التفاعلية -->
    <script>
        function updatePrice(button, price) {
            const parent = button.parentElement;
            const buttons = parent.querySelectorAll('.type-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            
            button.classList.add('active');
            
            const card = parent.parentElement.parentElement;
            const priceVal = card.querySelector('.price-val');
            priceVal.innerText = price;
        }

        function filterMenu(category) {
            const tabs = document.querySelectorAll('.tab-button');
            tabs.forEach(tab => tab.classList.remove('active'));
            event.currentTarget.classList.add('active');

            const mealsSec = document.getElementById('cat-meals');
            const pizzaSec = document.getElementById('cat-pizza');

            if (category === 'all') {
                mealsSec.style.display = 'block';
                pizzaSec.style.display = 'block';
            } else if (category === 'meals') {
                mealsSec.style.display = 'block';
                pizzaSec.style.display = 'none';
            } else if (category === 'pizza') {
                mealsSec.style.display = 'none';
                pizzaSec.style.display = 'block';
            }
        }
    </script>
</body>
</html>
