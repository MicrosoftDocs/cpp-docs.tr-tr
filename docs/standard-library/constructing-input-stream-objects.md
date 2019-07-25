---
title: Giriş Akışı Oluşturma Nesneleri
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: c000a9e927169ef710554372217ba15089ee11b8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457291"
---
# <a name="constructing-input-stream-objects"></a>Giriş Akışı Oluşturma Nesneleri

Yalnızca `cin` nesnesini kullanırsanız, bir giriş akışı oluşturmanız gerekmez. Şunu kullanırsanız bir giriş akışı oluşturmanız gerekir:

- [Giriş dosyası akış oluşturucuları](#vclrfinputfilestreamconstructorsanchor8)

- [Giriş dizesi akış oluşturucuları](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a>Giriş dosyası akış oluşturucuları

Bir giriş dosyası akışı oluşturmanın iki yolu vardır:

- **Void** bağımsız değişken oluşturucusunu kullanın, ardından `open` üye işlevini çağırın:

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

## <a name="vclrfinputstringstreamconstructorsanchor9"></a>Giriş dizesi akış oluşturucuları

Giriş dizesi akış oluşturucuları, önceden ayrılan, önceden başlatılmış depolamanın adresini gerektirir:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)
