---
title: Gecikmeli yüklenen DLL'i kaldırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724ee2ac3987c855f5e2102dee35d12785726641
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Kaldırma
Varsayılan sağlanan Gecikmeli Yükleme Yardımcısı gecikme yükü tanımlayıcıları bir işaretçi ve özgün içeri aktarma adres tablosunu (IAT) bir kopyasını pUnloadIAT alanına sahip olup olmadığını denetler. Bu durumda, onu bir işaretçi alma gecikme tanımlayıcısı listesinde kaydeder. Bu DLL'i açıkça kaldırma desteği adıyla DLL bulmak yardımcı işlevini etkinleştirir.  
  
 Gecikmeli yüklenen DLL'i açıkça kaldırma için İşlevler ve ilişkili yapıları şunlardır:  
  
```  
//  
// Unload support from delayimp.h  
//  
  
// routine definition; takes a pointer to a name to unload  
  
ExternC  
BOOL WINAPI  
__FUnloadDelayLoadedDLL2(LPCSTR szDll);  
  
// structure definitions for the list of unload records  
typedef struct UnloadInfo * PUnloadInfo;  
typedef struct UnloadInfo {  
    PUnloadInfo     puiNext;  
    PCImgDelayDescr pidd;  
    } UnloadInfo;  
  
// from delayhlp.cpp  
// the default delay load helper places the unloadinfo records in the   
// list headed by the following pointer.  
ExternC  
PUnloadInfo __puiHead;  
```  
  
 UnloadInfo yapısı kullanan bir C++ sınıfı kullanılarak uygulanır **LocalAlloc** ve **LocalFree** uygulamaları kendi işleci olarak **yeni** and işleci  **silme** sırasıyla. Bu seçenekler listesinde __puiHead listesi head kullanarak bir standart bağlantılı tutulur.  
  
 Arama __FUnloadDelayLoadedDLL adını bulmak deneyecek (tam bir eşleşme gereklidir) yüklenen DLL'ler listesinde sağlayın. PUnloadIAT IAT kopyasını bulundu, kopyalanır dönüştürücü işaretçileri geri yüklemek için çalışan IAT üst kitaplığı ile serbest **FreeLibrary**, eşleşen **UnloadInfo** kayıt bağlantısız Listenin silinmiş ve doğru döndürülür.  
  
 İşlev __FUnloadDelayLoadedDLL2 bağımsız değişkeni büyük küçük harfe duyarlıdır. Örneğin, şunu belirtmeniz gerekir:  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 ve değil:  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yardımcı İşlevini Anlama](understanding-the-helper-function.md)