---
title: Derleyici Uyarısı (düzey 4) C4266
ms.date: 11/04/2016
f1_keywords:
- C4266
helpviewer_keywords:
- C4266
ms.assetid: 90ec5f5b-3451-4c16-bb1b-c30a626bdaa0
ms.openlocfilehash: e192f2e138c7e586b0fbd05e83755e686b7749ad
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541676"
---
# <a name="compiler-warning-level-4-c4266"></a>Derleyici Uyarısı (düzey 4) C4266

' function ': temel ' Type ' öğesinden sanal üye işlevi için geçersiz kılma yok; işlev gizli

Türetilmiş bir sınıf, sanal bir işlevin tüm aşırı yüklerini geçersiz kılmadı.

Bu uyarı varsayılan olarak kapalıdır.  Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4266 oluşturur:

```cpp
// C4266.cpp
// compile with: /W4 /c
#pragma warning (default : 4266)
class Engine {
public:
   virtual void OnException(int&,int);
   virtual void OnException(int&,int&,int);
};

class LocalBinding : private Engine {
   virtual void OnException(int&,int);
};   // C4266
```

Olası çözüm:

```cpp
// C4266b.cpp
// compile with: /W4 /c
#pragma warning (default : 4266)
class Engine {
public:
   virtual void OnException(int&,int);
   virtual void OnException(int&,int&,int);
};

class LocalBinding : private Engine {
   virtual void OnException(int&,int);
   virtual void OnException(int&, int&, int);
};
```