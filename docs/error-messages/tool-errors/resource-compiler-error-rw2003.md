---
title: Kaynak Derleyicisi Hatası RW2003
ms.date: 11/04/2016
f1_keywords:
- RW2003
helpviewer_keywords:
- RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
ms.openlocfilehash: 60e813fff46ebc015f281dfed99d2916ca0eb4bb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190618"
---
# <a name="resource-compiler-error-rw2003"></a>Kaynak Derleyicisi Hatası RW2003

Oluşturma hatası

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. **Hata: bit eşlem dosyası kaynağı-dosya 3,00 biçiminde değil**

   Windows sürüm 2. x biçimini kullanan bit eşlemler sürüm 3. x kaynak dosyalarında kullanılamaz. Bit eşlem yeniden çizilmeli veya 3. x biçimine dönüştürülmelidir.

1. **Hata: kaynak adında eski DIB. SDK PAINT üzerinden geçirin**

   Belirtilen kaynaktaki cihazdan bağımsız bit eşlem (DIB), Windows 3,0 biçimiyle uyumlu değil. Bit eşlem yeniden çizilmeli veya 3. x biçimine dönüştürülmelidir.

1. **Hata: kaynak dosyası kaynağı-ad 3,00 biçiminde değil**

   Belirtilen kaynaktaki bir simge veya imleç, önceki bir Windows sürümünden biçim kullandı. Simge veya imleç yeniden çizilmeli veya 3. x biçimine dönüştürülmelidir.

1. **Bilinmeyen DIB üst bilgi biçimi**

   Bit eşlem üstbilgisi bir BITMAPCOREHEADER veya BITMAPıNFOHEADER yapısı değil.

1. **Sembol bilgileri başlatılamadı**

   Bu hata yalnızca görselde C++oluşur. Olası nedeni çok fazla açık dosya olabilir veya betiğinizdeki sembolleri içeri aktarmak üzere Visual C++ için gereken veri dosyalarını açamıyor veya yazamaz. Görsel C++ , bu dosyaları **tmp** ortam değişkeni tarafından belirtilen dizinde veya hiçbiri belirtilmemişse geçerli dizin ile oluşturmaya çalışır.

1. **Sembol bilgisi kaydedilemiyor**

   Bu hata yalnızca görselde C++oluşur. Olası nedeni çok fazla açık dosya olabilir veya betiğinizdeki sembolleri içeri aktarmak üzere Visual C++ için gereken veri dosyalarını kapatamıyor veya yazamaz. Görsel C++ , bu dosyaları **tmp** ortam değişkeni veya hiçbiri belirtilmemişse geçerli dizin tarafından belirtilen dizinde kullanmaya çalışır.

1. **Bit eşlem dosyası kaynak dosyası 2,03 biçiminde değil**

   Bit eşlem 2,03 sürümünden önceki bir biçimi kullandı. Bit eşlem, sürüm 3,00 veya üzeri biçimi kullanılarak dönüştürülmelidir veya yeniden çizmelidir.

1. **Kaynak çok büyük**

   Windows 3,1 için bir kaynak yaklaşık 65000 baytı aşamaz. Kaynağınız varsa, görsel C++ veya komut satırı kaynak derleyicisi ile derleyemeyeceksiniz. Bu sınır imleçler, simgeler, bit eşlemler veya dosya tabanlı diğer kaynaklar için geçerlidir.

1. **Kaynak dosyası 3,00 biçiminde değil**

   Bir imleç veya simge 3,00 sürümünden önceki bir biçimi kullandı. Kaynak, sürüm 3,00 veya üzeri biçimi kullanılarak dönüştürülmelidir veya yeniden çizmeli.

1. **Geçici dosya açılamıyor**

   Kaynak derleyicisi/Visual C++ , geçici bir dosya açamadı. Olası nedeni, dizin için yazma izinleriniz yok veya dizin yok. Kaynak derleyicisi/görsel C++ bu dosyaları, **tmp** ortam değişkeni tarafından belirtilen dizinde veya hiçbiri belirtilmemişse geçerli dizin ile kullanmayı dener.
