---
title: "Kaynak Derleyicisi hatası RW2003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW2003
dev_langs:
- C++
helpviewer_keywords:
- RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f388ca21d95e7d675a6b9890a7368765b5c0d7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2003"></a>Kaynak Derleyicisi Hatası RW2003
Oluşturma hatası  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  **Hata: Bit eşlem kaynak dosya 3.00 biçiminde değil.**  
  
     Bit eşlemler Windows sürümü 2.x biçimini kullanarak sürüm 3.x kaynak dosyalarında kullanılamaz. Bit eşlem yeniden düzenlenmiş veya 3.x biçimine dönüştürülür.  
  
2.  **Hata: Eski DIB kaynak adı. SDKPAINT geçirin**  
  
     Bir aygıt bağımsız bit eşlem (DIB) belirtilen kaynak Windows 3.0 biçimiyle uyumlu değil. Bit eşlem yeniden düzenlenmiş veya 3.x biçimine dönüştürülür.  
  
3.  **Hata: Kaynak dosya kaynak adı 3.00 biçiminde değil.**  
  
     Önceki bir Windows sürümü biçiminden bir simgesi veya imleci belirtilen kaynak kullanılır. Simgesi veya imleci yeniden düzenlenmiş veya gerekir 3.x biçimine dönüştürülür.  
  
4.  **Bilinmeyen DIB üstbilgi biçimi**  
  
     Bit eşlem üstbilgi BITMAPCOREHEADER veya BITMAPINFOHEADER yapısını değil.  
  
5.  **Sembol bilgilerini başlatılamadı**  
  
     Bu hata, yalnızca Visual c++'ta oluşur. Olası neden, çok fazla açık dosya sahip veya açamaz veya komut dosyanızı sembolleri almak Visual C++ için gerekli veri dosyaları yazma değil. Visual C++ girişimleri tarafından belirtilen dizinde bu dosyaları oluşturmak **TMP** ortam değişkeni veya hiçbiri belirtilmezse geçerli dizin.  
  
6.  **Sembol bilgileri kaydedilemiyor**  
  
     Bu hata, yalnızca Visual c++'ta oluşur. Olası neden, çok fazla açık dosya sahip veya kapatın veya komut dosyanızı sembolleri almak Visual C++ için gerekli veri dosyaları yazma değil. Visual C++ girişimleri tarafından belirtilen dizinde bu dosyaları kullanmak **TMP** ortam değişkeni veya hiçbiri belirtilmezse geçerli dizin.  
  
7.  **Bit eşlem dosyası kaynak 2.03 biçiminde değil**  
  
     Bir bit eşlem sürüm 2.03'den önceki bir biçim kullanılır. Bit eşlem dönüştürülen veya yeniden düzenlenmiş 3.00 sürümü için aşağıdaki biçimi kullanarak veya üzeri olması gerekir.  
  
8.  **Kaynak çok büyük**  
  
     Windows 3.1 için bir kaynak yaklaşık 65000 baytı aşamaz. Kaynak gruplarınız varsa, daha sonra Visual C++ veya komut satırı kaynak derleyicisi ile derleme mümkün olmaz. Bu sınır imleçler, simgeler, bit eşlemler veya dosya tabanlı kaynaklar için geçerli değildir.  
  
9. **Kaynak dosyası 3.00 biçiminde değil**  
  
     Bir biçim sürüm 3.00'den önceki bir imleç veya simge kullanılır. Kaynak dönüştürülen veya yeniden düzenlenmiş 3.00 sürümü için aşağıdaki biçimi kullanarak veya üzeri olması gerekir.  
  
10. **Geçici dosya açılamıyor**  
  
     Kaynak Derleyicisi/Visual C++, geçici bir dosya açamadı. Olası neden dizini için yazma izinlerine sahip değil veya dizin mevcut değil. Kaynak Derleyicisi/Visual C++ tarafından belirtilen dizinde bu dosyaları kullanma girişiminde **TMP** ortam değişkeni veya hiçbiri belirtilmezse geçerli dizin.