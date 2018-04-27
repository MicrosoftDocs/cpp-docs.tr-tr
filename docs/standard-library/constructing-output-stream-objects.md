---
title: Çıkış akış nesnelerini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: debc39987efffe149b8b7834ba5416027acadf4e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="constructing-output-stream-objects"></a>Çıkış Akış Nesnelerini Oluşturma

Yalnızca önceden tanımlanmış kullanırsanız `cout`, `cerr`, veya `clog` nesneleri, çıkış akışına oluşturmak gerekmez. Oluşturucuları için kullanmanız gerekir:

- [Çıkış dosya akışı oluşturucular](#vclrfoutputfilestreamconstructorsanchor1)

- [Çıkış dizesi akış oluşturucular](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Çıkış dosya akışı oluşturucular

Çıkış dosya akışı iki yoldan biriyle oluşturabileceğiniz:

- Varsayılan bir oluşturucu kullanın ve ardından arama `open` üye işlevi.

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Bir dosya adı ve modu bayrakları Oluşturucusu çağrısında belirtin.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Çıkış dizesi akış oluşturucular

Bir çıkış dizesi akışı oluşturmak için kullanabileceğiniz `ostringstream` şu şekilde:

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

`ends` "Manipulator" gerekli sonlandırma null karakter dizesi olarak ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
