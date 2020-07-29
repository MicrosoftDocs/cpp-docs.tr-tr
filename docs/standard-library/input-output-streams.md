---
title: Giriş çıkış akışları
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
ms.openlocfilehash: 54b53f96d487e466106fe92a01affa7bd3e55c16
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228264"
---
# <a name="inputoutput-streams"></a>Giriş/Çıkış Akışları

`basic_iostream`üst bilgi dosyasında tanımlanan, \<istream> hem giriş hem de çıkış karakter tabanlı g/ç akışlarını işleyen nesneler için sınıf şablonudur.

' In karaktere özgü uzmanlık düzeyini tanımlayan iki tür tanımları vardır `basic_iostream` ve kodun okunmasını kolaylaştırın: `iostream` (üst bilgi dosyası ile karıştırılmamalıdır), temel alan bir g/ç \<iostream> akışıdır `basic_iostream<char>` `wiostream` `basic_iostream<wchar_t>` .

Daha fazla bilgi için bkz. [Basic_iostream Class](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md)ve [wiostream](../standard-library/basic-iostream-class.md).

Öğesinden türetme `basic_iostream` `basic_fstream` , dosyalarından karakter verilerini akışa almak için kullanılan sınıf şablonudur.

Ayrıca, karaktere özgü uzmanlık sağlayan tür tanımları öğeleri de vardır `basic_fstream` . Bunlar, ve ' a dayalı bir dosya g/ç akışı olan bir `fstream` dosya g/ç akışıdır **`char`** `wfstream` **`wchar_t`** . Daha fazla bilgi için bkz. [Basic_fstream Class](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md)ve [wfstream](../standard-library/basic-fstream-class.md). Bu tür tanımları 'ın kullanılması için üst bilgi dosyasının eklenmesi gerekir \<fstream> .

> [!NOTE]
> `basic_fstream`Dosya g/ç 'yi gerçekleştirmek için bir nesne kullanıldığında, temeldeki arabellek okuma ve yazma için ayrı olarak belirlenmiş konumlar içerse de, geçerli giriş ve geçerli çıkış konumları birlikte bağlanır ve bu nedenle bazı verilerin okunması çıkış konumunu taşır.

Sınıf şablonu `basic_stringstream` ve ortak özelleştirmesi, `stringstream` genellikle karakter verilerini eklemek ve ayıklamak için g/ç Stream nesneleriyle çalışmak üzere kullanılır. Daha fazla bilgi için bkz. [Basic_stringstream sınıfı](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[stringstream](../standard-library/basic-stringstream-class.md)\
[basic_stringstream sınıfı](../standard-library/basic-stringstream-class.md)\
[\<sstream>](../standard-library/sstream.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
