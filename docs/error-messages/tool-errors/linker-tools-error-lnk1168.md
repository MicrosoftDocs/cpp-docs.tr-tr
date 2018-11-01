---
title: Bağlayıcı Araçları Hatası LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: d18aacd23a7ce9ed49f12a62f8358bb6d668c778
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622124"
---
# <a name="linker-tools-error-lnk1168"></a>Bağlayıcı Araçları Hatası LNK1168

yazma için dosya adı açılamıyor

Bağlayıcı yazılamıyor `filename`. Dosya kullanımda olabilir ve kendi dosya tanıtıcısı başka bir işlem tarafından kilitli olabilir ya da dosya için veya içinde bulunduğu dizin ya da ağ paylaşımı için yazma izniniz olmayabilir. Bu hata genellikle geçici bir durum nedeniyle — Örneğin, bir kilidi açık tutulduğu bir virüsten koruma programı tarafından bir dosya arama dizinleme işlemi veya bir kilidin serbest bir gecikme Visual Studio derleme sistemi tarafından tutulan.

Bu sorunu gidermek için aşağıdakileri doğrulayın `filename` dosya tanıtıcısı kilitli olmadığını ve dosya için yazma izniniz olduğunu. Yürütülebilir bir dosya ise, zaten yürütülmekte olmadığını doğrulayın.

Windows SysInternals yardımcı programları kullanabileceğiniz [işlemek](http://technet.microsoft.com/sysinternals/bb896655.aspx) veya [Process Explorer](http://technet.microsoft.com/sysinternals/bb896653) kilit üzerinde dosya tanıtıcısı işlemi belirlemek için `filename`. Process Explorer'ı, açık dosya tanıtıcılarındaki kilitleri serbest bırakmak için de kullanabilirsiniz. Bu yardım programlarının nasıl kullanılacağıyla ilgili bilgi için, beraberinde gelen Yardım dosyalarına göz atın.

Dosya, virüsten koruma programı tarafından kilitlenmişse, virüs koruma programıyla yapı çıktı dizinlerinizi otomatik taramanın dışında tutarak bu sorunu çözebilirsiniz. Anti-virüs tarayıcıları çoğunlukla dosya sisteminde yeni dosyaların oluşturulmasıyla tetiklenir ve tarama devam ederken kilitleri dosyalar üzerinde tutar. Belirli dizinleri taramanın dışında nasıl tutacağınız hakkındaki ayrıntılar için, virüsten koruma programı belgelerinize bakın.

Dosya, arama dizinleme hizmeti tarafından kilitlenmişse, yapı çıktı dizinlerinizi otomatik dizinlemenin dışında tutarak bu sorunu giderebilirsiniz. Daha fazla bilgi için dizinleme hizmetiyle ilgili belgelere başvurun. Windows Arama Dizin Oluşturma Hizmeti değiştirmek için kullanın **dizinleme seçeneklerini** Windows içinde **Denetim Masası**. Daha fazla bilgi için [geliştirmek Windows dizini kullanarak arar: sık sorulan sorular](http://windows.microsoft.com/windows/improve-windows-searches-using-index-faq#1TC=windows-7).

Yürütülebilir dosyanızın üzerine yapı işlemi tarafından yazılamıyorsa, dosyanız Dosya Gezgini tarafından kilitlenmiş olabilir. Varsa **uygulama deneyimi** hizmeti devre dışı bırakıldı, dosya Gezgini'nde bir yürütülebilir dosya tanıtıcı kilidine uzun bir süre tutunabilir. Bu sorunu gidermek için çalıştırın **services.msc** açın **özellikleri** iletişim kutusu için **uygulama deneyimi** hizmeti. Değişiklik **başlangıç türü** gelen **devre dışı bırakılmış** için **el ile**.
