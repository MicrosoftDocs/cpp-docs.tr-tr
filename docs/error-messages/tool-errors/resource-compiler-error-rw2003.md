---
title: Kaynak Derleyicisi Hatası RW2003
ms.date: 11/04/2016
f1_keywords:
- RW2003
helpviewer_keywords:
- RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
ms.openlocfilehash: f359c1f71f03ce0d946579776230398fb31d046f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396796"
---
# <a name="resource-compiler-error-rw2003"></a>Kaynak Derleyicisi Hatası RW2003

Oluşturma hatası

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. **Hata: Bit eşlem dosyası kaynak dosya 3.00 biçimde değil.**

   Windows sürüm 2.x biçimini kullanarak bit eşlemler sürüm 3.x kaynak dosyalarında kullanılamaz. Bit eşlem yeniden veya 3.x biçimine dönüştürüldü.

1. **Hata: Eski DIB kaynak adı. SDKPAINT geçirin**

   Bir cihaz bağımsız bit eşlem (DIB) belirtilen kaynak Windows 3.0 biçimiyle uyumlu değil. Bit eşlem yeniden veya 3.x biçimine dönüştürüldü.

1. **Hata: Kaynak dosya kaynak adı 3.00 biçimde değil.**

   Bir simgesi veya imleci belirtilen kaynağında Windows daha önceki bir sürümünden bir biçimi kullanılır. Simgesi veya imleci yeniden veya gerekir 3.x biçimine dönüştürüldü.

1. **Bilinmeyen DIB üstbilgi biçimi**

   Bit eşlem üst bilgisi BITMAPCOREHEADER veya BITMAPINFOHEADER yapısı değil.

1. **Sembol bilgisi başlatılamadı**

   Yalnızca Visual C++'da bu hata oluşur. Olası neden, çok fazla açık dosya olması veya açılamıyor veya Visual c++'ın betiğinizin sembolleri içeri aktarmak gerekli veri dosyaları yazma ' dir. Visual C++ tarafından belirtilen dizindeki bu dosyaların oluşturulması girişimlerini **TMP** ortam değişkeninde ya da hiçbiri belirtilmezse geçerli dizin.

1. **Sembol bilgisi kaydedilemiyor**

   Yalnızca Visual C++'da bu hata oluşur. Olası neden, çok fazla açık dosya olması veya kapatın veya Visual c++'ın betiğinizin sembolleri içeri aktarmak gerekli veri dosyaları yazma ' dir. Visual C++ tarafından belirtilen dizindeki bu dosyaları kullanmak girişimlerini **TMP** ortam değişkeninde ya da hiçbiri belirtilmezse geçerli dizin.

1. **Bit eşlem dosyası kaynak 2.03 biçimde değil.**

   Bir bit eşlem 2.03 sürümden önceki bir biçimi kullanılır. Bit eşlem dönüştürülmüş veya yeniden düzenlenmiş sürüm 3.00 için aşağıdaki biçimi kullanarak ya da üzeri olması gerekir.

1. **Kaynak çok büyük**

   Windows 3.1 için bir kaynak yaklaşık 65000 baytı aşamaz. Kaynağınız varsa, daha sonra Visual C++ ya da komut satırı kaynak derleyicisi ile derlemek mümkün olmayacaktır. Bu sınırı imleçler, simgeler, bit eşlemler veya diğer dosya tabanlı kaynaklar için geçerli değildir.

1. **Kaynak dosyası 3.00 biçimde değil.**

   Bir biçim sürüm 3.00'den önceki bir işaretçi veya simge kullanılır. Kaynak, dönüştürülen veya yeniden düzenlenmiş sürüm 3.00 için aşağıdaki biçimi kullanarak veya üzeri olmalıdır.

1. **Geçici dosya açılamıyor**

   Kaynak Derleyici/Visual C++, geçici bir dosya açamadı. Olası neden, dizin için yazma izinlerine sahip değil ya da dizin yok değil. Kaynak Derleyici/Visual C++ tarafından belirtilen dizin içinde bu dosyaları kullanmayı dener **TMP** ortam değişkeninde ya da hiçbiri belirtilmezse geçerli dizin.