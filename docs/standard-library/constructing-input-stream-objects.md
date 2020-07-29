---
title: Giriş Akışı Oluşturma Nesneleri
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: f281741979680fc03d3f96d2dbfbac6e1feefdea
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228316"
---
# <a name="constructing-input-stream-objects"></a>Giriş Akışı Oluşturma Nesneleri

Yalnızca `cin` nesnesini kullanırsanız, bir giriş akışı oluşturmanız gerekmez. Şunu kullanırsanız bir giriş akışı oluşturmanız gerekir:

- [Giriş dosyası akış oluşturucuları](#vclrfinputfilestreamconstructorsanchor8)

- [Giriş dizesi akış oluşturucuları](#vclrfinputstringstreamconstructorsanchor9)

## <a name="input-file-stream-constructors"></a><a name="vclrfinputfilestreamconstructorsanchor8"></a>Giriş dosyası akış oluşturucuları

Bir giriş dosyası akışı oluşturmanın iki yolu vardır:

- **`void`** Bağımsız değişken oluşturucusunu kullanın, ardından `open` üye işlevini çağırın:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Oluşturucu çağrısında bir dosya adı ve mod bayrakları belirtin, bu nedenle dosyayı oluşturma işlemi sırasında açmanız gerekir:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="input-string-stream-constructors"></a><a name="vclrfinputstringstreamconstructorsanchor9"></a>Giriş dizesi akış oluşturucuları

Giriş dizesi akış oluşturucuları, önceden ayrılan, önceden başlatılmış depolamanın adresini gerektirir:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş akışları](../standard-library/input-streams.md)
