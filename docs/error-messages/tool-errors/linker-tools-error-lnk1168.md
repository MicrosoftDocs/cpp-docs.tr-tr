---
title: Bağlayıcı Araçları Hatası LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: f0eb63c124162dbb515782bbd014c556c12de153
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450894"
---
# <a name="linker-tools-error-lnk1168"></a>Bağlayıcı Araçları Hatası LNK1168

yazma için dosya adı açılamıyor

Bağlayıcı yazılamıyor `filename`. Dosya kullanımda olabilir ve kendi dosya tanıtıcısı başka bir işlem tarafından kilitli olabilir ya da dosya için veya içinde bulunduğu dizin ya da ağ paylaşımı için yazma izniniz olmayabilir. Bu hata genellikle geçici bir durum nedeniyle — Örneğin, bir kilidi açık tutulduğu bir virüsten koruma programı tarafından bir dosya arama dizinleme işlemi veya bir kilidin serbest bir gecikme Visual Studio derleme sistemi tarafından tutulan.

Bu sorunu gidermek için aşağıdakileri doğrulayın `filename` dosya tanıtıcısı kilitli olmadığını ve dosya için yazma izniniz olduğunu. Yürütülebilir bir dosya ise, zaten yürütülmekte olmadığını doğrulayın.

Windows SysInternals yardımcı programları kullanabileceğiniz [işlemek](/sysinternals/downloads/handle) veya [Process Explorer](/sysinternals/downloads/process-explorer) kilit üzerinde dosya tanıtıcısı işlemi belirlemek için `filename`. Process Explorer'ı, açık dosya tanıtıcılarındaki kilitleri serbest bırakmak için de kullanabilirsiniz. Bu yardım programlarının nasıl kullanılacağıyla ilgili bilgi için, beraberinde gelen Yardım dosyalarına göz atın.

Dosya, virüsten koruma programı tarafından kilitlenmişse, virüs koruma programıyla yapı çıktı dizinlerinizi otomatik taramanın dışında tutarak bu sorunu çözebilirsiniz. Anti-virüs tarayıcıları çoğunlukla dosya sisteminde yeni dosyaların oluşturulmasıyla tetiklenir ve tarama devam ederken kilitleri dosyalar üzerinde tutar. Belirli dizinleri taramanın dışında nasıl tutacağınız hakkındaki ayrıntılar için, virüsten koruma programı belgelerinize bakın.

Dosya, arama dizinleme hizmeti tarafından kilitlenmişse, yapı çıktı dizinlerinizi otomatik dizinlemenin dışında tutarak bu sorunu giderebilirsiniz. Daha fazla bilgi için dizinleme hizmetiyle ilgili belgelere başvurun. Windows Arama Dizin Oluşturma Hizmeti değiştirmek için kullanın **dizinleme seçeneklerini** Windows içinde **Denetim Masası**. Daha fazla bilgi için [arama Windows 10'da dizin oluşturma: SSS](https://support.microsoft.com/help/4098843/windows-10-search-indexing-faq).

Yürütülebilir dosyanızın üzerine yapı işlemi tarafından yazılamıyorsa, dosyanız Dosya Gezgini tarafından kilitlenmiş olabilir. Varsa **uygulama deneyimi** hizmeti devre dışı bırakıldı, dosya Gezgini'nde bir yürütülebilir dosya tanıtıcı kilidine uzun bir süre tutunabilir. Bu sorunu gidermek için çalıştırın **services.msc** açın **özellikleri** iletişim kutusu için **uygulama deneyimi** hizmeti. Değişiklik **başlangıç türü** gelen **devre dışı bırakılmış** için **el ile**.
