---
description: "Daha fazla bilgi edinin: Delay-Loaded DLL 'yi kaldırma"
title: Gecikmeli Yüklenen DLL'i Kaldırma
ms.date: 11/04/2016
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
ms.openlocfilehash: fd733bfa02a6d90eecb1b617288d368d33766282
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178946"
---
# <a name="unloading-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL'i Kaldırma

Varsayılan olarak sağlanan Gecikmeli Yükleme Yardımcısı, gecikme yükü tanımlayıcılarının bir işaretçiye sahip olup olmadığını ve pUnloadIAT alanında orijinal içeri aktarma adres tablosunun (ıAT) bir kopyasını olup olmadığını denetler. Bu durumda, bir listedeki işaretçiyi içeri aktarma gecikmesi tanımlayıcısına kaydeder. Bu, yardımcı işlevin dll 'yi açıkça kaldırmayı desteklemek için DLL adını adıyla bulmasını sağlar.

Bir Gecikmeli yüklenen DLL 'yi açıkça kaldırma ile ilgili yapılar ve işlevler aşağıda verilmiştir:

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

UnloadInfo yapısı, konum operatörü ve işleci olarak **LocalAlloc** ve **LocalFree** uygulamalarını kullanan bir C++ sınıfı kullanılarak uygulanır **`new`** **`delete`** . Bu seçenekler, listenin başı olarak __puiHead kullanılarak standart bağlantılı bir listede tutulur.

__FUnloadDelayLoadedDLL çağırmak, yüklenen dll 'Ler listesinde sağladığınız adı bulmayı dener (tam eşleşme gerekir). Bulunursa, ıAT 'ın pUnloadIAT içindeki kopyası, dönüştürücü işaretçilerini geri yüklemek için çalışan ıAT 'ın üzerine kopyalanır, kitaplık **FreeLibrary** ile serbest bırakılır, eşleşen **UnloadInfo** kaydının LISTEDE bağlantısı kaldırılır ve doğru döndürülür.

İşlevin __FUnloadDelayLoadedDLL2 bağımsız değişkeni büyük/küçük harfe duyarlıdır. Örneğin şunu belirtmeniz gerekir:

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

değil:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı Işlevini anlama](understanding-the-helper-function.md)
