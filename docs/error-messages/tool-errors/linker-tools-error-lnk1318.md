---
title: Bağlayıcı Araçları Hatası LNK1318
ms.date: 05/29/2018
f1_keywords:
- LNK1318
helpviewer_keywords:
- LNK1318
ms.openlocfilehash: 8ed6489a27d4c0e117f7f18281ff188f40936e0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160997"
---
# <a name="linker-tools-error-lnk1318"></a>Bağlayıcı Araçları Hatası LNK1318

> Beklenmeyen PDB hatası; *neden* '*ayrıntıları*'

Bağlayıcı açarken, okuma veya bir PDB dosyasına yazılırken beklenmeyen bir hatayla karşılaştı.

Bu hata iletisi, PDB dosyalarında genel olmayan sorunlar için oluşturulur. *Neden* ve *ayrıntıları* hatanın oluştuğu andaki kullanılabilir bilgi bağlayıcıya temsil eder. Bu ayrı, daha açıklayıcı hata iletileri PDB dosyaları uğraşmanızı olduğunda genel hata olarak çok yararlı olmayabilir.

Hatanın kaynağını seyrek olduğundan yalnızca genel öneriler bu sorunu çözümlemek için kullanılabilir:

- Derleme dizinlerinizde temizleme işlemi gerçekleştirin ve sonra çözümünüzün tam bir derleme yapın.

- Bilgisayarınızı yeniden başlatmanız veya gereksiz veya askıda mspdbsrv.exe işlemleri için denetleyin ve bunları Görev Yöneticisi ' sonlandırılır.

- Proje dizinlerinizi virüsten koruma denetimlerini devre dışı bırakın.

- Kullanım [/Zf](../../build/reference/zf.md) kullanıyorsanız derleyici seçeneği [/MP](../../build/reference/mp-build-with-multiple-processes.md) MSBuild veya başka bir paralel derleme işlemi.

- Yapı, 64 bitlik barındırılan araç takımını kullanarak deneyin.

- Gerekirse paralel bağlantı sorunlarını gidermek için bağlama serileştirir. Mspdbsrv.exe bağlantı bir örneği tarafından başlatılır ve başka bir örneğinin bağlantı yapılmadan önce kapatıldığında bu hataya neden olabilir, kullanarak. Bu düzeltme dezavantajı, proje derlemelerinizi tamamlanması oldukça uzun sürebilir ' dir.