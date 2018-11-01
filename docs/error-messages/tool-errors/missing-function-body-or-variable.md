---
title: Eksik İşlev Gövdesi veya Değişken
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 88470272192520e9aa0582fd06ff36a0542803ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647128"
---
# <a name="missing-function-body-or-variable"></a>Eksik İşlev Gövdesi veya Değişken

Yalnızca bir işlev prototipi ile derleyici hatasız devam edebilirsiniz, ancak hiçbir işlev kodu veya değişken boşluk ayrılmış olduğundan bağlayıcı bir çağrı bir adrese çözümlenemiyor. Bağlayıcı çözümlenmelidir işlevi çağrısı oluşturabilir, bu hatayı göremez.

## <a name="example"></a>Örnek

Exists işlevi düşünmek derleyici prototip izin verdiğinden ana işlev çağrısında LNK2019 neden olur.  Bağlayıcı değil olduğunu bulur.

```
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>Örnek

C++'da, bir sınıf ve yalnızca bir prototip için belirli bir işlev uygulaması'nı sınıf tanımında eklediğinizden emin olun. Üstbilgi dosyasının dışında sınıfı tanımlıyorsanız, sınıf adı işlevinden önce eklediğinizden emin olun (`Classname::memberfunction`).

```
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)