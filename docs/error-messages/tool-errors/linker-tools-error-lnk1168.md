---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1168'
title: Bağlayıcı Araçları Hatası LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: 692bfbcc744307f32c8017b41ec27f5f421ea17c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253500"
---
# <a name="linker-tools-error-lnk1168"></a>Bağlayıcı Araçları Hatası LNK1168

yazma için dosya adı açılamıyor

Bağlayıcı öğesine yazılamıyor `filename` . Dosya kullanımda olabilir ve kendi dosya tanıtıcısı başka bir işlem tarafından kilitli olabilir ya da dosya için veya içinde bulunduğu dizin ya da ağ paylaşımı için yazma izniniz olmayabilir. Bu hata genellikle geçici bir koşul nedeniyle oluşur — Örneğin, bir virüsten koruma programı tarafından tutulan bir kilit, bir dosya arama dizin oluşturma işlemi veya Visual Studio yapı sistemi tarafından tutulan bir kilidi serbest bırakma gecikmesi.

Bu sorunu onarmak için `filename` Dosya tanıtıcısının kilitli olduğunu ve dosya için yazma izninizin olduğunu doğrulayın. Yürütülebilir bir dosya ise, zaten yürütülmekte olmadığını doğrulayın.

Hangi işlemin bir dosya tanıtıcısı kilidi olduğunu anlamak için Windows SysInternals yardımcı programları [işleyicisini](/sysinternals/downloads/handle) veya [işlem Gezginini](/sysinternals/downloads/process-explorer) kullanabilirsiniz `filename` . Process Explorer'ı, açık dosya tanıtıcılarındaki kilitleri serbest bırakmak için de kullanabilirsiniz. Bu yardım programlarının nasıl kullanılacağıyla ilgili bilgi için, beraberinde gelen Yardım dosyalarına göz atın.

Dosya, virüsten koruma programı tarafından kilitlenmişse, virüs koruma programıyla yapı çıktı dizinlerinizi otomatik taramanın dışında tutarak bu sorunu çözebilirsiniz. Anti-virüs tarayıcıları çoğunlukla dosya sisteminde yeni dosyaların oluşturulmasıyla tetiklenir ve tarama devam ederken kilitleri dosyalar üzerinde tutar. Belirli dizinleri taramanın dışında nasıl tutacağınız hakkındaki ayrıntılar için, virüsten koruma programı belgelerinize bakın.

Dosya, arama dizinleme hizmeti tarafından kilitlenmişse, yapı çıktı dizinlerinizi otomatik dizinlemenin dışında tutarak bu sorunu giderebilirsiniz. Daha fazla bilgi için dizinleme hizmetiyle ilgili belgelere başvurun. Windows Search dizin oluşturma hizmetini değiştirmek için Windows **Denetim Masası**'Ndaki **Dizin oluşturma seçeneklerini** kullanın. Daha fazla bilgi için bkz. [Windows 10 ' da arama dizini oluşturma: SSS](https://support.microsoft.com/help/4098843/windows-10-search-indexing-faq).

Yürütülebilir dosyanızın üzerine yapı işlemi tarafından yazılamıyorsa, dosyanız Dosya Gezgini tarafından kilitlenmiş olabilir. **Uygulama deneyimi** hizmeti devre dışıysa, dosya Gezgini uzun bir süre için yürütülebilir dosya tanıtıcı kilidine açık kalabilir. Bu sorunu onarmak için, **Services. msc** ' yi çalıştırın ve ardından **uygulama deneyimi** hizmeti 'nin **Özellikler** iletişim kutusunu açın. **Başlangıç türünü** **devre dışı** iken **el ile** olarak değiştirin.
