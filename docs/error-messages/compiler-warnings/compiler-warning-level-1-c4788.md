---
title: Derleyici Uyarısı (düzey 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 76a33b24446debffb2c00bf1b0497cfc86022ce0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175148"
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
