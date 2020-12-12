---
description: 'Hakkında daha fazla bilgi edinin: çıkış akışı nesneleri oluşturma'
title: Çıkış Akış Nesnelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: e730e4cb675b216fa56b5624feb69fadcd61400a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233649"
---
# <a name="constructing-output-stream-objects"></a>Çıkış Akış Nesnelerini Oluşturma

Yalnızca önceden tanımlanmış `cout` , `cerr` veya `clog` nesnelerini kullanırsanız, çıkış akışı oluşturmanız gerekmez. İçin oluşturucular kullanmanız gerekir:

- [Çıkış dosyası akış oluşturucuları](#vclrfoutputfilestreamconstructorsanchor1)

- [Çıkış dizesi akış oluşturucuları](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="output-file-stream-constructors"></a><a name="vclrfoutputfilestreamconstructorsanchor1"></a> Çıkış dosyası akış oluşturucuları

Bir çıkış dosyası akışını iki şekilde oluşturabilirsiniz:

- Varsayılan oluşturucuyu kullanın ve ardından `open` üye işlevini çağırın.

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Oluşturucu çağrısında bir dosya adı ve mod bayrakları belirtin.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="output-string-stream-constructors"></a><a name="vclrfoutputstringstreamconstructorsanchor2"></a> Çıkış dizesi akış oluşturucuları

Çıkış dizesi akışı oluşturmak için `ostringstream` aşağıdaki şekilde kullanabilirsiniz:

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

`ends`"İşleici", gereken sonlandırma null karakterini dizeye ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış akışları](../standard-library/output-streams.md)
