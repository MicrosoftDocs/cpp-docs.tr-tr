---
title: Çıkış Akış Nesnelerini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: 7da7d9dd0fae3ce3fa21ecd774f88643dca49c26
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440943"
---
# <a name="constructing-output-stream-objects"></a>Çıkış Akış Nesnelerini Oluşturma

Yalnızca tanımlanmış kullanırsanız `cout`, `cerr`, veya `clog` nesneler, bir çıkış akışı oluşturmak gerekmez. Oluşturucular için kullanmanız gerekir:

- [Çıkış dosyası Stream oluşturucular](#vclrfoutputfilestreamconstructorsanchor1)

- [Çıkış dizesi Stream oluşturucular](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Çıkış dosyası Stream oluşturucular

Bir çıkış dosya akışı iki yoldan biriyle oluşturabilirsiniz:

- Varsayılan Oluşturucu kullanın ve sonra çağrı `open` üye işlevi.

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Bir dosya adı ve modu bayrakları Oluşturucusu çağrısında belirtmektir.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Çıkış dizesi Stream oluşturucular

Bir çıkış dizesi akışı oluşturmak için kullanabileceğiniz `ostringstream` şu şekilde:

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

`ends` "İşleyici" gerekli sondaki boş karakter dizesi olarak ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
