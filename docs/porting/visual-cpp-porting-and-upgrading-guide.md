---
title: Microsoft C++ taşıma ve Yükseltme Kılavuzu
description: Microsoft C++ Code 'U Visual Studio 'nun en son sürümüne yükseltin.
ms.date: 11/18/2019
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: 723879ad03b9b66c7490804e890f07d6d55e9dae
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303339"
---
# <a name="microsoft-c-porting-and-upgrading-guide"></a>Microsoft C++ taşıma ve Yükseltme Kılavuzu

Bu makalede, Microsoft C++ kodunu Visual Studio 'nun en son sürümüne yükseltmeye yönelik bir kılavuz sağlanmaktadır. Visual Studio 2010 ile 2015 arasında oluşturulan projeler için Visual Studio 2019 ' de projeyi açmanız yeterlidir. Visual Studio 2008 veya önceki bir projeyi iki adımda yükseltebilirsiniz. İlk olarak projeyi MSBuild biçimine dönüştürmek için Visual Studio 2010 kullanın. Sonra Visual Studio 2019 ' de projeyi açın. Tüm yönergeler için bkz. [Visual C++ Studio 'nun önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md).

Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 içindeki Araç kümeleri ikili uyumludur. Artık kitaplık bağımlılıklarınızı yükseltebilmeniz gerekmeden derleyicinin daha yeni bir sürümüne yükseltebilirsiniz. Daha fazla bilgi için bkz [ C++ . ikili uyumluluk 2015-2019](binary-compat-2015-2017.md).

Açık kaynaklı kitaplıkları kullanan veya birden çok platformda çalışacak olan projeleri yükseltirken, CMake tabanlı bir projeye geçiş yapmanız önerilir. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md)

## <a name="reasons-to-upgrade-c-code"></a>Kodu yükseltme C++ nedenleri

Eski bir uygulama çalışır durumda, güvenli bir ortamda çalışır ve etkin geliştirme kapsamında değilse, bunu yükseltmek çok daha özenli olmayabilir. Ancak, şu durumlarda bir yükseltmeyi düşünün: uygulamanız devam eden bakım gerektirir. Ya da yeni özellik geliştirme yapıyor veya performans ya da güvenlik iyileştirmeleri yapıyor olabilirsiniz. Yükseltme şu avantajları sunar:

- Derleyici iyileştirmelerini geliştirdiğimiz için aynı kod daha hızlı çalışabilir.

- Modern C++ Özellikler ve programlama uygulamaları hataların yaygın nedenlerini ortadan kaldırır ve eski C stili deyimlerinin korunması çok daha kolay olan kodlar üretir.

- Derleme süreleri, derleyicide ve bağlayıcıdaki performans geliştirmelerinden daha hızlıdır.

- Daha iyi standartlar uygunluğu. [/Permissive-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği, geçerli C++ standarda uygun olmayan kodu tanımlamanızı sağlar.

- Daha güvenli [C çalışma zamanı kitaplığı](../c-runtime-library/security-features-in-the-crt.md) özellikleri de dahil olmak üzere daha iyi çalışma zamanı güvenliği. Ve [koruma denetimi](../build/reference/guard-enable-guard-checks.md) ve adres Temizleme (Visual Studio 2019 sürüm 16,4 ' de yenidir) gibi derleyici özellikleri.

## <a name="multitargeting-vs-upgrading"></a>Çoklu hedefleme ve yükseltme

Kod tabanınızı yeni bir araç takımına yükseltmek sizin için bir seçenek değildir. Daha eski araç kümeleri ve kitaplıklar kullanan projeler oluşturmak ve düzenlemek için en son Visual Studio 'Yu kullanmaya devam edebilirsiniz. Visual Studio 2019 ' de, şu özelliklerden yararlanabilirsiniz:

- kaynak kodunuzda olası sorunları belirlemenize yardımcı olmak C++ Için temel yönergeler denetleyicileri ve Clang-Tidy dahil olmak üzere modern statik analiz araçları.

- modern stilleri seçiminize göre otomatik biçimlendirme, eski kodların çok daha okunaklı olmasına yardımcı olabilir.

Daha fazla bilgi için bkz. [Eski projeler oluşturmak Için Visual Studio 'da yerel çoklu sürüm kullanımını kullanma](use-native-multi-targeting.md).

## <a name="in-this-section"></a>Bu bölümde

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual C++ Studio 'nun önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Kod tabanınızı Visual Studio 2019 ve derleyicinin v142 sürümüne yükseltme.|
|[Kod yükseltmek C++ için IDE araçları](ide-tools-for-upgrading-code.md)|Yükseltme sürecinde yardımcı olan yararlı IDE özellikleri.|
|[C++ikili uyumluluk 2015-2019](binary-compat-2015-2017.md)|V140 ve v141 kitaplıklarını v142 projelerinden olduğu gibi kullanın.|
|[Visual Studio’da Eski Projeleri Oluşturmak için Yerel Çoklu Sürüm Paketi Kullanma](use-native-multi-targeting.md)|Daha eski derleyiciler ve kitaplıklarla Visual Studio 2019 kullanın.|
|[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)|Microsoft C++ kitaplıklarında yapılan tüm değişikliklerin listesi ve Visual Studio 2003 ile 2015 arasındaki derleme araçları, kodunuzda değişiklik yapılmasını gerektirebilir.|
|[Visual C++ 2003 ile 2015 Arasındaki Farklar](visual-cpp-what-s-new-2003-through-2015.md)|Visual Studio 2015 aracılığıyla Visual Studio 2003 ' den Microsoft C++ 'a yönelik "yenilikler" bilgileri.|
|[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](porting-and-upgrading-examples-and-case-studies.md)|Bu bölümde, birkaç örnek ve uygulama ele alınmıştır ve bu deneyimleri ve sonuçları tartıştık. Bu makaleler, taşıma ve yükseltme sürecinde nelerin yer aldığı hakkında fikir verir. İşlemin tamamında, yükseltme için ipuçları ve püf noktaları tartışıyoruz ve belirli hataların düzeltilme şeklini gösteririz.|
|[Evrensel Windows Platformu taşıma](porting-to-the-universal-windows-platform-cpp.md)|Windows 10 ' a kod taşıma hakkında bilgi içerir|
|[UNIX Kullanıcıları için Visual C++'a Giriş](introduction-to-visual-cpp-for-unix-users.md)|Görsele C++ yenı olan UNIX kullanıcıları için bilgi sağlar ve bu verilerle üretken olmak ister.|
|[Windows 'da Linux programlarını çalıştırma](porting-from-unix-to-win32.md)|UNIX uygulamalarının Windows 'a geçirilmesi için seçenekleri açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[Visual Studio 'daki C++ derleyicide yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)<br/>
