---
title: Derleyici Uyarısı (Düzey 3) C4398 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c38ade6b75242fdd5144481e3415e914cb6773c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704620"
---
# <a name="compiler-warning-level-3-c4398"></a>Derleyici Uyarısı (Düzey 3) C4398

> '*değişkeni*': işlem içi genel nesne ile birden çok appdomains oluşturuyor doğru çalışmayabilir; __declspec(appdomain) kullanmayı düşünün

## <a name="remarks"></a>Açıklamalar

Sanal işlevle [__clrcall](../../cpp/clrcall.md) yerel tür çağırma oluşturulmasını neden olan bir uygulama etki alanı vtable başına. Bu tür bir değişken doğru birden çok uygulama etki alanlarında kullanıldığında düzeltebilir değil.

Açıkça değişkeni işaretleyerek bu uyarıyı çözümleyebilirsiniz `__declspec(appdomain)`. Visual Studio 2017 önce Visual Studio sürümlerinde, bu uyarı ile derleme tarafından çözebilirsiniz **/CLR: pure**, varsayılan olarak genel değişkenler appdomain başına yapar. **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md) ve [uygulama etki alanları ve Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4398 oluşturur.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```