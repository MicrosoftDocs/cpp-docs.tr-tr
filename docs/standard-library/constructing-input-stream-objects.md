---
title: Giriş akışı nesneleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7066ffe50dc76c26528e7bfcd3dc9e9778e1473a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="constructing-input-stream-objects"></a>Giriş Akışı Oluşturma Nesneleri

Yalnızca kullanıyorsanız `cin` nesnesi, bir giriş akışı oluşturmak gerekmez. Kullanırsanız, bir giriş akışı oluşturmalıdır:

- [Giriş dosyası akış oluşturucular](#vclrfinputfilestreamconstructorsanchor8)

- [Giriş dizesi akış oluşturucular](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> Giriş dosyası akış oluşturucular

Bir giriş dosya akışı oluşturmanın iki yolu vardır:

- Kullanım `void` bağımsız değişkeni oluşturucusu,'ı çağırın `open` üye işlevi:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Böylece oluşturma işlemi sırasında dosya açılırken Oluşturucusu çağrısı filename ve modu bayrakları belirtin:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> Giriş dizesi akış oluşturucular

Giriş dizesi akış oluşturucular ön tahsis, preinitialized depolama adresini gerektirir:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
