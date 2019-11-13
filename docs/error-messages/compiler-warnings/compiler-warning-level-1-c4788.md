---
title: Derleyici Uyarısı (düzey 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 03ce38aaa910a410025c5cccdf39646d34104779
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052385"
---
# <a name="compiler-warning-level-1-c4788"></a>Derleyici Uyarısı (düzey 1) C4788

' tanımlayıcı ': tanımlayıcı ' number ' karakter olarak kesildi

Derleyici, bir işlev adı için izin verilen uzunluk üst sınırını sınırlandırır. Derleyici, EH/SEH kodu için funclets oluşturduğunda, işlev adını bazı metinler (örneğin, "__catch", "\__unwind" veya başka bir dize) ile önceden bekleyen, funclet 'inde sembol adını oluşturur.

Elde edilen funclet 'inde sembol adı çok uzun olabilir ve derleyici onu keser ve C4788 oluşturur.

Bu uyarıyı çözmek için özgün işlev adını kısaltın. İşlev bir C++ şablon işlevi veya yöntemi ise, adın bir parçası olarak bir typedef kullanın. Örneğin:

```cpp
C1<x, y, z<T>>::C2<a,b,c>::f
```

Şu şekilde değiştirilebilir:

```cpp
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

Bu uyarı yalnızca x64 derleyicisinde oluşur.