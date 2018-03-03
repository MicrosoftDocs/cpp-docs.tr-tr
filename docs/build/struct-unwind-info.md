---
title: UNWIND_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1effec5bc753f1b23f8d43a8406c61cb6663fa56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="struct-unwindinfo"></a>struct UNWIND_INFO
Bırakma veri bilgisi yapısı yığın işaretçisi ve kalıcı Yazmaçları yığında kaydedildiği bir işleve sahiptir etkileri kaydetmek için kullanılır:  
  
|||  
|-|-|  
|UBYTE: 3|Sürüm|  
|UBYTE: 5|Bayraklar|  
|UBYTE|Giriş boyutu|  
|UBYTE|Bırakma kodlarının sayımı|  
|UBYTE: 4|Çerçeve kaydı|  
|UBYTE: 4|Çerçeve kaydı uzaklığı (ölçekli)|  
|USHORT * n|Bırakma kodları dizisi|  
|değişken|Ya da formun (1) veya (2) aşağıda olabilir mi|  
  
 (1) özel durum işleyicisi  
  
|||  
|-|-|  
|ULONG|Özel durum işleyici adresi|  
|değişken|Dile özel işleyici veriler (isteğe bağlı)|  
  
 (2) Zincirleme Bırakma bilgisi  
  
|||  
|-|-|  
|ULONG|Başlangıç adresi işlevi|  
|ULONG|İşlev bitiş adresi|  
|ULONG|Bırakma bilgisi adresi|  
  
 UNWIND_INFO yapısı bellekte DWORD hizalanmış olmalıdır. Her bir alan anlamını aşağıdaki gibidir:  
  
 **Sürüm**  
 Bırakma verisinin, şu anda 1 sürüm numarası.  
  
 **Bayrakları**  
 Üç bayrakları şu anda tanımlanmıştır:  
  
 Özel durumlar incelemek için gereken işlevleri ararken çağrılmalıdır bir özel durum işleyicisi UNW_FLAG_EHANDLER işlevi vardır.  
  
 UNW_FLAG_UHANDLER Bu işlev bir özel durum geriye doğru izleme zaman çağrılmalıdır sonlandırma işleyicisi vardır.  
  
 UNW_FLAG_CHAININFO bu bırakma bilgisi yapısı birincil bir yordam için değil. Bunun yerine, zincirleme girdisi önceki bir RUNTIME_FUNCTION içeriğini giriştir bırakma bilgisi. Aşağıdaki metni bir açıklaması için bkz: zincirleme bırakma bilgi yapıları. Bu bayrağı ayarlarsanız UNW_FLAG_EHANDLER ve UNW_FLAG_UHANDLER bayrakları temizlenmelidir. Ayrıca, çerçeve kayıt ve sabit yığın ayırma alanları bilgilerindeki birincil aynı değerlere sahip olmalıdır.  
  
 **Giriş boyutu**  
 İşlev giriş bayt cinsinden uzunluğu.  
  
 **Bırakma kodlarının sayımı**  
 Bırakma kodları dizisi yuvalarında sayısıdır. Bazı kodları (örneğin, UWOP_SAVE_NONVOL) bırakma Not dizideki birden fazla yuvası gerektirir.  
  
 **Çerçeve kaydı**  
 Sıfır olmayan, ardından işlevi bir çerçeve işaretçisi kullanır ve bu alan için işlem bilgileri alan UNWIND_CODE düğümlerinin aynı kodlama kullanılarak çerçeve işaretçisi olarak kullanılan kalıcı kayıt sayısıdır.  
  
 **Çerçeve kaydı uzaklığı (ölçekli)**  
 Çerçeve yazmaç alanı sıfır değilse, ardından oluşturulduğunda, FP reg uygulanan RSP ölçeklendirilmiş uzaklığı budur. Gerçek FP reg ayarlamak RSP + 16 * 240 0'dan uzaklıkları izin vererek, bu sayı. Bu, dinamik yığın çerçeveleri, daha iyi kod yoğunluğu kısa yönergeleri (daha fazla yönerge 8 bit imzalanmış sapma formu kullanabilirsiniz) aracılığıyla izin vermek için yerel yığın ayırma ortasına FP reg işaret eden izin verir.  
  
 **Bırakma kodları dizisi**  
 Bu giriş etkisini kalıcı yazmaçlar ve RSP açıklayan bir öğe dizisidir. Öğelerin tek tek anlamları için UNWIND_CODE hakkındaki bakın. Hizalama amacıyla, bu dizinin her zaman bir çift sayı (Bu durumda dizi sayısı bırakma kodları alanı tarafından belirtilenden daha uzun bir olacaktır), en son girişi potansiyel olarak kullanılmayan girişlerinin olacaktır.  
  
 **Özel durum işleyici adresi**  
 Bu işlevin dile özgü özel durum/sonlandırma işleyicisi için bir resim göreli işaretçidir (UNW_FLAG_CHAININFO bayrağı Temizle ve UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER bayrakları birini ayarlanır) olur.  
  
 **Dile özel işleyici verileri**  
 Bu işlevin dile özgü özel durum işleyici verilerdir. Bu veri biçimi belirtilmemiş ve tamamen kullanımda bir özel durum işleyici tarafından belirlenir.  
  
 **Zincirleme Bırakma bilgisi**  
 UNW_FLAG_CHAININFO bayrağı ayarlarsanız UNWIND_INFO yapısı üç UWORDs ile sona erer.  Bu UWORDs işlevi zincirleme RUNTIME_FUNCTION bilgilerini temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)