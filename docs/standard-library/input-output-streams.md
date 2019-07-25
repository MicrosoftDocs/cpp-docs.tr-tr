---
title: Giriş çıkış akışları
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
ms.openlocfilehash: 3d5344ede3a62375c4c8102d1fc39445518eb0c4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455265"
---
# <a name="inputoutput-streams"></a>Giriş/Çıkış Akışları

`basic_iostream`IStream > başlık dosyasında \<tanımlanan, hem giriş hem de çıkış karakter tabanlı g/ç akışlarını işleyen nesneler için sınıf şablonudur.

' In karaktere özgü uzmanlık `basic_iostream` düzeyini tanımlayan iki tür tanımları vardır ve kodun okunmasını kolaylaştırabilir: `iostream` (üst bilgi > dosyasıyla \<karıştırılmamalıdır), temel alan `basic_iostream<char>`bir g/ç akışıdır. , temelli bir g/ç akışıdır. `basic_iostream<wchar_t>` `wiostream`

Daha fazla bilgi için bkz. [Basic_iostream Class](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md)ve [wiostream](../standard-library/basic-iostream-class.md).

Öğesinden `basic_iostream` türetme, dosyalarından karakter verilerini `basic_fstream`akışa almak için kullanılan sınıf şablonudur.

Ayrıca, `basic_fstream`karaktere özgü uzmanlık sağlayan tür tanımları öğeleri de vardır. Bunlar, **char**'a dayalı bir dosya g/ç akışı, yani wchar_t 'yi temel alan bir g/ç akışı olan bir dosya g/ç akışıdır.  `fstream` `wfstream` Daha fazla bilgi için bkz. [Basic_fstream Class](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md)ve [wfstream](../standard-library/basic-fstream-class.md). Bu tür tanımları 'ın kullanılması için, fstream > Üstbilgi \<dosyasının eklenmesi gerekir.

> [!NOTE]
> Dosya g `basic_fstream` /ç 'yi gerçekleştirmek için bir nesne kullanıldığında, temeldeki arabellek okuma ve yazma için ayrı olarak belirlenmiş konumlar içerse de, geçerli giriş ve geçerli çıkış konumları birlikte bağlanır ve bu nedenle bazı verileri okumak için çıkış konumu.

Sınıf şablonu `basic_stringstream` ve ortak `stringstream`özelleştirmesi, genellikle karakter verilerini eklemek ve ayıklamak için g/ç Stream nesneleriyle çalışmak üzere kullanılır. Daha fazla bilgi için bkz. [Basic_stringstream Class](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[stringstream](../standard-library/basic-stringstream-class.md)\
[basic_stringstream sınıfı](../standard-library/basic-stringstream-class.md)\
[\<sstream >](../standard-library/sstream.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
