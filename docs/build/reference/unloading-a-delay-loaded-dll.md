---
title: Gecikmeli Yüklenen DLL'i Kaldırma
ms.date: 11/04/2016
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
ms.openlocfilehash: ac23a82282215e70a6895e021d25437bc8890c6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460651"
---
# <a name="unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Kaldırma

Varsayılan olarak sağlanan gecikme yük yardımcı gecikme yükü tanımlayıcıları pUnloadIAT alanında bir işaretçi ve orijinal içeri aktarma adres tablosunda (IAT) bir kopyasını olup olmadığını denetler. Bu durumda, bir işaretçi alma gecikme tanımlayıcı listesinde kaydeder. Bu, söz konusu DLL'i açıkça kaldırma desteklemek için ad tarafından DLL bulmak yardımcı işlevini sağlar.

Gecikmeli yüklenen DLL'i açıkça kaldırma işlevlerini ve ilişkili yapıları şunlardır:

```cpp
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

UnloadInfo yapısını kullanan bir C++ sınıfı kullanılarak uygulanan **LocalAlloc** ve **LocalFree** uygulamalarını, işleci olarak **yeni** ve işleci  **silme** sırasıyla. Bu seçenekler, listenin başındaki __puiHead kullanarak bir standart bağlantılı listesinde saklanır.

Adı bulmak arama __FUnloadDelayLoadedDLL deneyecek (tam bir eşleşme gereklidir) yüklü DLL'leri listesinde sağlayın. PUnloadIAT içinde IAT kopyası bulundu, kopyalanıp kopyalanmadığını dönüştürücü işaretçileri geri yüklemek için çalışan IAT üst, kitaplığı ile serbest **FreeLibrary**, eşleşen **UnloadInfo** kayıt bağlantısız Liste silindi ve TRUE olarak döndürülür.

Bağımsız değişken işlev __FUnloadDelayLoadedDLL2 büyük/küçük harfe duyarlıdır. Örneğin, şunu belirtmeniz gerekir:

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

ve değil:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>Ayrıca Bkz.

[Yardımcı İşlevini Anlama](understanding-the-helper-function.md)