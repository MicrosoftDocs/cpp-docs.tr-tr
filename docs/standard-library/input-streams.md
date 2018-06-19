---
title: Giriş akışı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3dff2e0bb0ee070b8b90ca3896d7bf8114ca918
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845576"
---
# <a name="input-streams"></a>Giriş Akışları

Giriş akışı nesneyi bayt bir kaynaktır. En önemli üç Giriş akışı sınıfları [IStream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md), ve [istringstream](../standard-library/basic-istringstream-class.md).

`istream` Sınıfı sıralı metin modu girişi için en iyi şekilde kullanılır. Sınıfının nesneleri yapılandırabilirsiniz `istream` için arabelleğe alınan veya arabellekten çıkarılan işlemi. Tüm temel sınıf işlevselliğini `ios`, yer aldığı `istream`. Nadiren sınıftan nesneleri oluşturmak `istream`. Bunun yerine, genellikle önceden tanımlanmış kullanacağınız `cin` gerçekten sınıfın bir nesnesi nesne [ostream](../standard-library/basic-ostream-class.md). Bazı durumlarda, atadığınız `cin` diğer akış nesnelere program başlatma sonra.

`ifstream` Sınıfı, disk dosya giriş destekler. Gerekirse bir yalnızca disk dosya, sınıfın bir nesnesi oluşturmak `ifstream`. İkili veya metin modu veri belirtebilirsiniz. Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda dosya otomatik olarak açılır. Aksi takdirde, kullanabileceğiniz `open` sonra varsayılan oluşturucu çağırma işlevi. Birçok biçimlendirme seçenekleri ve üye işlevlerini uygulamak `ifstream` nesneleri. Tüm temel sınıflar işlevselliğini `ios` ve `istream` dahil `ifstream`.

Gibi kitaplığı işlevi `sscanf_s`, `istringstream` sınıfı, bellek içi dizeleri girişten destekler. Null Sonlandırıcı sahip bir karakter dizisi veri ayıklamak için ayırın ve dizesini başlatır, sonra sınıfın bir nesnesi oluşturmak `istringstream`.

## <a name="in-this-section"></a>Bu Bölümde

[Giriş Akışı Oluşturma Nesneleri](../standard-library/constructing-input-stream-objects.md)

[Ayıklama İşleçlerini Kullanma](../standard-library/using-extraction-operators.md)

[Ayıklama Hataları için Test Yapma](../standard-library/testing-for-extraction-errors.md)

[Giriş Akışı Manipülatörleri](../standard-library/input-stream-manipulators.md)

[Giriş Akışı Üye İşlevleri](../standard-library/input-stream-member-functions.md)

[Kendi Sınıflarınız İçin >> İşleci Aşırı Yükleme](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>Ayrıca bkz.

[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
