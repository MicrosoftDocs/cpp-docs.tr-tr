---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4788'
title: Derleyici Uyarısı (düzey 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 2aa87fd8a09b9f308e7fbb51fc4f05792210b0c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234611"
---
# <a name="compiler-warning-level-1-c4788"></a>Derleyici Uyarısı (düzey 1) C4788

' tanımlayıcı ': tanımlayıcı ' number ' karakter olarak kesildi

Derleyici, bir işlev adı için izin verilen uzunluk üst sınırını sınırlandırır. Derleyici, EH/SEH kodu için funclets oluşturduğunda, işlev adını bazı metinler (örneğin, "__catch", " \_ _unwind" veya başka bir dize) ile önceden bekleyen, funclet 'inde sembol adını oluşturur.

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
