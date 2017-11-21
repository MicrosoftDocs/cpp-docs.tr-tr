---
title: "Çıkış akışları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c2a16e9125c0c121aea3905b6e20eba59ef1dc68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="output-streams"></a>Çıkış Akışları
Bir çıkış akışı bayt için bir hedef nesnesidir. Üç en önemli çıkış akışı sınıflardır `ostream`, `ofstream`, ve `ostringstream`.  
  
 `ostream` Sınıfı, türetilmiş sınıf üzerinden `basic_ostream`, önceden tanımlanmış akışı nesneleri destekler:  
  
-   `cout`standart çıktı  
  
-   `cerr`Standart sınırlı arabelleğe alma ile hata  
  
-   `clog`benzer şekilde `cerr` ancak tam arabelleğe alma  
  
 Nesneleri gelen oluşturulur nadiren `ostream`; önceden tanımlanmış nesneleri genellikle kullanılır. Bazı durumlarda, önceden tanımlanmış nesneler program başlatma işleminden sonra atayabilirsiniz. `ostream` Arabelleğe alınan veya arabellekten çıkarılan işlemi için yapılandırılabilir, sınıf, sıralı metin modu çıktı için uygundur. Tüm temel sınıf işlevselliğini `ios`, yer aldığı `ostream`. Sınıfın bir nesnesi oluşturmak, `ostream`, belirtmeniz gerekir bir `streambuf` oluşturucuya nesnesi.  
  
 `ofstream` Sınıfı, disk dosya çıktısı destekler. Yalnızca çıktı disk gerekiyorsa, sınıfın bir nesnesi oluşturmak `ofstream`. Belirleyebileceğiniz olup olmadığını `ofstream` nesneleri oluşturulurken, ikili veya metin modu verileri kabul `ofstream` nesne veya çağrılırken `open` nesnenin üye işlevi. Birçok biçimlendirme seçenekleri ve üye işlevlerini uygulamak `ofstream` nesneleri ve temel sınıflarının tüm işlevleri `ios` ve `ostream` bulunur.  
  
 Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda bu dosyayı otomatik olarak açılır. Aksi takdirde, kullanabileceğiniz `open` varsayılan oluşturucu çağırma sonra üye işlevi.  
  
 Çalışma zamanı işlevi gibi `sprintf_s`, `ostringstream` sınıfı, bellek içi dizeleri çıkışı destekler. Akış g/ç biçimlendirme kullanarak bellekte bir dize oluşturmak için sınıfın bir nesnesi oluşturmak `ostringstream`.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Çıkış akış nesnelerini oluşturma](../standard-library/constructing-output-stream-objects.md)  
  
 [Ekleme işleçlerini kullanma ve biçimi denetleme](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [Çıkış dosya akışı üye işlevleri](../standard-library/output-file-stream-member-functions.md)  
  
 [Ara belleğe almanın etkileri](../standard-library/effects-of-buffering.md)  
  
 [İkili çıktı dosyaları](../standard-library/binary-output-files.md)  
  
 [Aşırı yükleme << kendi sınıflarınız için işleci](../standard-library/overloading-the-output-operator-for-your-own-classes.md)  
  
 [Bağımsız değişkenler olmadan kendi Manipülatörlerinizi yazma](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## <a name="see-also"></a>Ayrıca Bkz. 
 [ofstream](../standard-library/basic-ofstream-class.md)   
 [ostringstream](../standard-library/basic-ostringstream-class.md)   
 [iostream programlama](../standard-library/iostream-programming.md)

