---
title: Microsoft C++ taşıma ve Yükseltme Kılavuzu
description: Microsoft C++ Code 'U Visual Studio 'nun en son sürümüne yükseltin.
ms.date: 11/05/2019
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: 04c3950d637c01031e78d0d95e13232143ceb232
ms.sourcegitcommit: 4dde7914608508e47c21cae03ac58fe953a0c29b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2019
ms.locfileid: "74119493"
---
# <a name="microsoft-c-porting-and-upgrading-guide"></a>Microsoft C++ taşıma ve Yükseltme Kılavuzu

Bu konuda, Microsoft C++ kodunu Visual Studio 'nun en son sürümüne yükseltmeye yönelik bir kılavuz sağlanmaktadır. Visual Studio 2008 veya önceki sürümlerde oluşturulan bir projeden yükseltiyorsanız, önce Visual Studio 2010 ' i kullanarak projeyi MSBuild biçimine dönüştürmeniz, ardından projeyi Visual Studio 2019 ' de açmanız gerekir. Visual Studio 2010 ile 2015 arasında oluşturulan projeler için Visual Studio 2019 ' de projeyi açmanız yeterlidir. Tüm yönergeler için bkz. [Visual C++ Studio 'nun önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md).

Visual Studio 2015 ' deki araç kümeleri, Visual Studio 2017 ve Visual Studio 2019 ikili uyumludur ve kitaplık bağımlılıklarını yükseltmek zorunda kalmadan derleyicinin daha yeni bir sürümüne yükseltmenizi sağlar. Daha fazla bilgi için bkz [ C++ . 2015 ve 2019 arasındaki ikili uyumluluk](binary-compat-2015-2017.md).

Açık kaynaklı kitaplıkları kullanan veya birden çok platformda çalışacak olan projeleri yükseltirken, CMake tabanlı bir projeye geçiş yapmanız önerilir. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md)

## <a name="reasons-to-upgrade-c-code"></a>Kodu yükseltme C++ nedenleri

Eski bir uygulama çalışır durumda, güvenli bir ortamda çalışır ve etkin geliştirme kapsamında değilse, bunu yükseltmek için çok daha özensiz bir sorun olabilir. Ancak, bir uygulama devam eden bakım veya performans veya güvenlik iyileştirmeleri dahil yeni özellik geliştirmesi gerektiriyorsa, aşağıdaki nedenlerden herhangi biri için kodu yükseltmeniz göz önüne alabilirsiniz:

- Aynı kod, geliştirilmiş derleyici iyileştirmeleri nedeniyle daha hızlı çalışabilir.

- Modern C++ Özellikler ve programlama uygulamaları, hataların yaygın olarak karşılaşılan nedenlerini ortadan kaldırır ve eski C stili deyimlerinin korunması çok daha kolay olan kodlar üretir.

- Derleme süreleri, derleyicide ve bağlayıcıdaki performans iyileştirmeleri nedeniyle önemli ölçüde daha hızlıdır.

- Daha iyi standartlar uygunluğu. [/Permissive-](../build/reference/permissive-standards-conformance.md) derleyici seçeneği, daha önce Microsoft C++ derleyicisi tarafından izin verilen ancak geçerli C++ standarda uygun olmayan kodu tanımlamanızı sağlar.

- Daha güvenli [C çalışma zamanı kitaplığı]() özellikleri ve [koruyucu denetimi](../build/reference/guard-enable-guard-checks.md) ve adres temizleme (Visual Studio 2019 sürüm 16,4) gibi derleyici özellikleri de dahil olmak üzere daha iyi çalışma zamanı güvenliği.

## <a name="multitargeting-vs-upgrading"></a>Çoklu hedefleme ve yükseltme

Kod tabanınızı yeni bir araç takımına yükseltmek bir seçenek değilse, daha eski araç kümeleri ve kitaplıkları ile derlenen projeleri derlemek ve düzenlemek için Visual Studio 'nun son sürümünü kullanmaya devam edebilirsiniz. Visual Studio 2019 ' de, şu özelliklerden yararlanabilirsiniz:

- kaynak kodunuzda olası sorunları belirlemenize yardımcı olmak C++ Için temel yönergeler denetleyicileri ve Clang-Tidy dahil olmak üzere modern statik analiz araçları.

- modern stilleri seçiminize göre otomatik biçimlendirme, eski kodların çok daha okunaklı olmasına yardımcı olabilir.

Daha fazla bilgi için bkz. [Eski projeler oluşturmak Için Visual Studio 'da yerel çoklu sürüm kullanımını kullanma](use-native-multi-targeting.md).

## <a name="in-this-section"></a>Bu bölümde

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual C++ Studio 'nun önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Kod tabanınızı Visual Studio 2019 ve derleyicinin v142 sürümüne yükseltme.|
|[Kod yükseltmek C++ için IDE araçları](ide-tools-for-upgrading-code.md)|Yükseltme sürecinde yardımcı olan yararlı IDE özellikleri.|
|[C++2015 ile 2019 arasında ikili uyumluluk](binary-compat-2015-2017.md)|V140 kitaplıklarını v142 projelerinden olduğu gibi kullanın.|
|[Visual Studio’da Eski Projeleri Oluşturmak için Yerel Çoklu Sürüm Paketi Kullanma](use-native-multi-targeting.md)|Daha eski derleyiciler ve kitaplıklarla Visual Studio 2019 kullanın.|
|[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)|Microsoft C++ kitaplıklarında yapılan tüm değişikliklerin listesi ve Visual Studio 2003 ile 2015 arasındaki derleme araçları, kodunuzda değişiklik yapılmasını gerektirebilir.|
|[Visual C++ 2003 ile 2015 Arasındaki Farklar](visual-cpp-what-s-new-2003-through-2015.md)|Visual Studio 2015 aracılığıyla Visual Studio 2003 ' den Microsoft C++ 'a yönelik "yenilikler" bilgileri.|
|[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](porting-and-upgrading-examples-and-case-studies.md)|Bu bölümde, birkaç örnek ve uygulama ele alınmıştır ve bu deneyimleri ve sonuçları tartıştık. Bunları okumayı, taşıma ve yükseltme sürecinde nelerin bulunduğunu anlabileceğinizi fark edebilirsiniz. İşlemin tamamında, yükseltme için ipuçları ve püf noktaları tartışıyoruz ve belirli hataların düzeltilme şeklini gösteririz.|
|[Evrensel Windows Platformu taşıma](porting-to-the-universal-windows-platform-cpp.md)|Windows 10 ' a kod taşıma hakkında bilgi içerir|
|[UNIX Kullanıcıları için Visual C++'a Giriş](introduction-to-visual-cpp-for-unix-users.md)|Görsele C++ yenı olan UNIX kullanıcıları için bilgi sağlar ve bu verilerle üretken olmak ister.|
|[Windows 'da Linux programlarını çalıştırma](porting-from-unix-to-win32.md)|UNIX uygulamalarının Windows 'a geçirilmesi için seçenekleri açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[Visual Studio 'daki C++ derleyicide yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)<br/>
