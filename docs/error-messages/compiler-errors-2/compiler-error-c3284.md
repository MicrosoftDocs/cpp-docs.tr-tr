---
title: Derleyici Hatası C3284 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6be84043d7c475cbd023d870e524f7bf9e6190
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105225"
---
# <a name="compiler-error-c3284"></a>Derleyici Hatası C3284

'function' işlevinin 'parametresi' genel parametresinin kısıtlamalarıyla 'function' işlevinin ' parametresi' genel parametresinin kısıtlamalarıyla eşleşmelidir

Genel bir sanal işlev ile aynı ada ve temel sınıfta bağımsız değişken kümesinin sanal işlevi olarak aynı kısıtlamalara kullanmanız gerekir.

Aşağıdaki örnek, C3284 oluşturur:

```
// C3284.cpp
// compile with: /clr /c
// C3284 expected
public interface class IGettable {
   int Get();
};

public interface class B {
   generic<typename T>
   where T : IGettable
   virtual int mf(T t);
};

public ref class D : public B {
public:
   generic<typename T>
   // Uncomment the following line to resolve.
   // where T : IGettable
   virtual int mf(T t) {
      return 4;
   }
};
```