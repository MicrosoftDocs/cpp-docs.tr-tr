---
title: __raise | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __raise
- __raise_cpp
dev_langs:
- C++
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abe0c1a2e443e88879cd7005d944acfcacc3c17d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031476"
---
# <a name="raise"></a>__raise

Bir olayın çağrı sitesini vurgular.

## <a name="syntax"></a>Sözdizimi

```
__raise method-declarator;
```

## <a name="remarks"></a>Açıklamalar

Yönetilen koddan bir olay yalnızca tanımlandığı sınıfın içinden oluşturulabilir. Bkz: [olay](../windows/event-cpp-component-extensions.md) daha fazla bilgi için.

Anahtar sözcüğü **__raise** dışı bir olay çağırırsanız yayılan bir hataya neden olur.

> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Olay İşleme](../cpp/event-handling.md)<br/>
[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)