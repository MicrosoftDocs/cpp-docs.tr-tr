---
title: Giriş Akışı Oluşturma Nesneleri
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: 89d681f1a092957bc966d2ec788a0f9aa2261ada
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543682"
---
# <a name="constructing-input-stream-objects"></a>Giriş Akışı Oluşturma Nesneleri

Yalnızca kullandığınız `cin` nesnesi, bir giriş akışı oluşturmak gerekmez. Kullanırsanız, bir giriş akışı oluşturmalıdır:

- [Giriş dosyası Stream oluşturucular](#vclrfinputfilestreamconstructorsanchor8)

- [Giriş dizesinin Stream oluşturucular](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> Giriş dosyası Stream oluşturucular

Bir giriş dosya akışı oluşturmanın iki yolu vardır:

- Kullanım **void** bağımsız değişken oluşturucusu, ardından çağırın `open` üye işlevi:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Böylece oluşturma işlemi sırasında dosya açma oluşturucu çağrısı, bir dosya adı ve modu bayrakları belirtin:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> Giriş dizesinin Stream oluşturucular

Giriş dizesinin stream oluşturucular ön tahsis, preinitialized depolama adresini gerektirir:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
