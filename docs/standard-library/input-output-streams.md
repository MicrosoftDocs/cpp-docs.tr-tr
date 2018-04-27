---
title: Giriş-Çıkış akışları | Microsoft Docs
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
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b38306bbedce82a1060bc0aa375e471838c0474
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="inputoutput-streams"></a>Giriş/Çıkış Akışları

`basic_iostream`, üstbilgi dosyasında tanımlanan \<IStream >, her ikisi de işlemek nesneleri giriş ve çıkış karakter tabanlı g/ç akışlarını sınıfı şablon aranır.

Karakter özgü özelleştirmeleri, tanımlayan iki tür tanımları vardır `basic_iostream` ve kod okunmasını kolaylaştırmak yardımcı olabilir: `iostream` (üstbilgi dosyası ile karıştırılmamalıdır \<iostream >) temel alan bir g/ç akışı `basic_iostream<char>`; `wiostream` temel alan bir g/ç akışı `basic_iostream<wchar_t>`.

Daha fazla bilgi için bkz: [basic_iostream sınıfı](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md), ve [wiostream](../standard-library/basic-iostream-class.md).

Öğesinden türetilen `basic_iostream` sınıf şablonu `basic_fstream`, gelen ve giden dosyaları karakter veri akışı için kullanılır.

Ayrıca vardır, özel karakter özelleştirmeleri sağlamak tür tanımları `basic_fstream`. Bunlar `fstream`, temel alan bir dosya g/ç akışı olduğu `char`, ve `wfstream`, temel alan bir dosya g/ç akışı olduğu `wchar_t`. Daha fazla bilgi için bkz: [basic_fstream sınıfı](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md), ve [wfstream](../standard-library/basic-fstream-class.md). Bu tür tanımları kullanılması üst bilgi dosyasını dahil edilmesi \<fstream >.

> [!NOTE]
> Zaman bir `basic_fstream` nesnesi, dosya g/ç gerçekleştirmek için kullanılır, temel alınan arabellek ayrı olarak içerse de okuma ve yazma, konumlarını belirlenmiş geçerli girişi ve geçerli çıkış konumlar birbirine bağlıdır ve bu nedenle, bazı veriler okunurken taşır Çıktı konumu.

Sınıf şablonu `basic_stringstream` ve kendi ortak uzmanlık `stringstream`, genellikle eklemek ve karakter veri ayıklamak için g/ç akışı nesneleri ile çalışmak için kullanılır. Daha fazla bilgi için bkz: [basic_stringstream sınıfı](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[stringstream](../standard-library/basic-stringstream-class.md)<br/>
[basic_stringstream Sınıfı](../standard-library/basic-stringstream-class.md)<br/>
[\<sstream >](../standard-library/sstream.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
