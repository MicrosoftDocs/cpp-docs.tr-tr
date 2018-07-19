---
title: Giriş-Çıkış akışları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcb17eeaf09cec63392cb842f790504b28038487
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955728"
---
# <a name="inputoutput-streams"></a>Giriş/Çıkış Akışları

`basic_iostream`, üstbilgi dosyasında tanımlanan \<istream >, her ikisini birden işlemek nesneleri giriş ve çıkış karakter tabanlı g/ç akışlarını sınıf şablonudur.

Özel karakter uzmanlıklarını tanımlayın iki tür tanımları vardır `basic_iostream` ve kod kolay okunur hale getirmenize yardımcı olabilir: `iostream` (üst bilgi dosyası ile karıştırılmamalıdır \<iostream >) temel alan bir g/ç akışı `basic_iostream<char>`; `wiostream` temel alan bir g/ç akışı `basic_iostream<wchar_t>`.

Daha fazla bilgi için [basic_iostream sınıfı](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md), ve [wiostream](../standard-library/basic-iostream-class.md).

Öğesinden türetilen `basic_iostream` sınıf şablonu `basic_fstream`, için ve dosyalarından karakter veri akışı için kullanılır.

Ayrıca vardır karakter özgü uzmanlıkları sağlayan bir tür tanımları `basic_fstream`. Bunlar `fstream`, temel alan bir dosya g/ç akışı olduğu **char**, ve `wfstream`, temel alan bir dosya g/ç akışı olduğu **wchar_t**. Daha fazla bilgi için [basic_fstream sınıfı](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md), ve [wfstream](../standard-library/basic-fstream-class.md). Bu tür tanımlarından kullanılması üstbilgi dosyasının eklenmesi \<fstream >.

> [!NOTE]
> Olduğunda bir `basic_fstream` nesnesi, dosya g/ç gerçekleştirmek için kullanılır, temel alınan arabellek ayrı olarak içerse de konumlarını okuma ve yazma, için belirtilen geçerli giriş ve çıkış geçerli konumlar birbirine bağlıdır ve bu nedenle, bazı verileri okuma taşır. Çıkış konumu.

Sınıf şablonu `basic_stringstream` ve kendi ortak uzmanlığı `stringstream`, genellikle eklemek ve karakter verileri ayıklamak için g/ç akışı nesneleri ile çalışmak için kullanılır. Daha fazla bilgi için [basic_stringstream sınıfı](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[stringstream](../standard-library/basic-stringstream-class.md)<br/>
[basic_stringstream Sınıfı](../standard-library/basic-stringstream-class.md)<br/>
[\<sstream >](../standard-library/sstream.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
