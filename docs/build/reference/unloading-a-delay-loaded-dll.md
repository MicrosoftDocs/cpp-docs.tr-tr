---
description: Gecikmeli yüklenen DLL 'yi kaldırma hakkında daha fazla bilgi edinin
title: Gecikmeli yüklenen DLL 'yi kaldırma
ms.date: 01/19/2021
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.openlocfilehash: 2ac898d56609ebb3aadc57ea8df00fa63fcbc3f0
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667241"
---
# <a name="unload-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL 'yi kaldırma

Varsayılan Gecikmeli Yükleme Yardımcısı, gecikme yükleme tanımlayıcılarının bir işaretçiye sahip olup olmadığını ve alanda orijinal içeri aktarma adresi tablosunun (ıAT) bir kopyasına sahip olup olmadığını denetler `pUnloadIAT` . Bu durumda, yardımcı, bir listedeki işaretçiyi içeri aktarma gecikmesi tanımlayıcısına kaydeder. Bu giriş, yardımcı işlevin dll 'yi ada göre bulmasını sağlar ve bu DLL 'yi açıkça kaldırmayı destekler.

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

`UnloadInfo`Yapı, `LocalAlloc` sırasıyla ve gibi uygulamalar kullanan bir C++ sınıfı kullanılarak uygulanır `LocalFree` `operator new` `operator delete` . Bu seçenekler, listenin başı olarak kullanılan standart bağlantılı bir listede tutulur `__puiHead` .

`__FUnloadDelayLoadedDLL`' İ çağırdığınızda, yüklenen dll 'ler listesinde sağladığınız adı bulmaya çalışır. (Tam eşleşme gereklidir.) Bulunursa, içindeki ıAT 'nin kopyası, `pUnloadIAT` dönüştürücü işaretçilerini geri yüklemek için çalışan IAT 'nin üstüne kopyalanır. Ardından, kitaplık kullanılarak serbest bırakılır `FreeLibrary` , eşleşen `UnloadInfo` kaydın listede bağlantısı kaldırılır ve silinir ve `TRUE` döndürülür.

İşlevin bağımsız değişkeni `__FUnloadDelayLoadedDLL2` büyük/küçük harfe duyarlıdır. Örneğin şunu belirtmeniz gerekir:

```cpp
__FUnloadDelayLoadedDLL2("user32.dll");
```

değil:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı işlevini anlama](understanding-the-helper-function.md)
