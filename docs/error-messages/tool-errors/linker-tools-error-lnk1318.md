---
title: Bağlayıcı Araçları Hatası LNK1318
ms.date: 05/29/2018
f1_keywords:
- LNK1318
helpviewer_keywords:
- LNK1318
ms.openlocfilehash: cce2c03783039a62b5cb6f60ecf8d76b23589483
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446719"
---
# <a name="linker-tools-error-lnk1318"></a>Bağlayıcı Araçları Hatası LNK1318

> Beklenmeyen PDB hatası; *neden* '*Ayrıntılar*'

Bağlayıcı, bir PDB dosyasını açarken, okurken veya yazarken beklenmeyen bir hatayla karşılaştı.

Bu hata iletisi PDB dosyalarındaki yaygın olmayan sorunlar için oluşturulur. *Nedeni* ve *ayrıntıları* , hata oluştuğunda bağlayıcının kullanabildiği bilgileri temsil eder. Bu çok yararlı olmayabilir, çünkü PDB dosyalarıyla ilgilenirken sık karşılaşılan hatalar ayrı, daha bilgilendirici hata iletileri vardır.

Hatanın kaynağı seyrek olduğundan, bu sorunu çözmek için yalnızca genel öneri mevcuttur:

- Yapı dizinlerinizde temiz bir işlem gerçekleştirin ve ardından çözümünüzün tam bir derlemesini yapın.

- Bilgisayarınızı yeniden başlatın veya boş veya yanıt vermeyen mspdbsrv.exe süreçlerini denetleyip TaskManager 'da sonlandırın.

- Proje dizinlerinizde virüsten koruma denetimlerini devre dışı bırakın.

- MSBuild ile [/MP](../../build/reference/mp-build-with-multiple-processes.md) ya da başka bir paralel yapı işlemi kullanıyorsanız [/ZF](../../build/reference/zf.md) derleyici seçeneğini kullanın.

- 64 bitlik barındırılan araç takımını kullanarak oluşturmayı deneyin.

- Gerektiğinde paralel bağlantı sorunlarını azaltmak için bağlamayı serileştirme. Bu hata, mspdbsrv.exe bir bağlantı örneği tarafından başlatılmışsa ve başka bir bağlantı örneği kullanılarak kapanmadan önce kapalıysa oluşur. Bu düzeltmeyle ilgili dezavantajı, proje derlemelerinizin tamamlanması önemli ölçüde uzun sürebilir.
