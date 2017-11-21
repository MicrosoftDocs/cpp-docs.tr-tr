---
title: "directory_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
dev_langs: C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: 9782cd4853b7b0c1f429f65ec0741148cc1bc241
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="directoryiterator-class"></a>directory_iterator Sınıfı
Bir dizin adlarında aracılığıyla dizilerinin giriş yineleyici açıklar. Yineleyici X, ifade için * X hesaplar için dosya adını ve durumunu hakkında bilinen herhangi bir şey sarmalar sınıfı directory_entry bir nesne.  
  
 Tür yolu, burada Dizinim sıralı için dizin adını temsil eder, exposition amaçları doğrultusunda adlı bir nesne ve türü directory_entry dizini geçerli dosya adını temsil eden myentry burada adlı bir nesne sınıfı depolar dizisi. Tür directory_entry oluşturulan varsayılan nesnesinin boş Dizinim pathname sahiptir ve bitiş dizisi yineleyici temsil eder.  
  
 Örneğin, dizin verilen abc girişleri def ve GHI, kodu ile:  
  
 `for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`  
  
 Çağrı bağımsız değişkenleri path("abc/def") ve path("abc/ghi") ziyaret edecektir.  
  
 Daha fazla bilgi ve kod örnekleri için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class directory_iterator;  
```  
  
## <a name="directoryiteratordirectoryiterator"></a>directory_iterator::directory_iterator  
  
```  
directory_iterator() noexcept;  
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;  
directory_iterator(const directory_iterator&) = default;  
directory_iterator(directory_iterator&&) noexcept = default;  
```  
  
 Bitiş dizisi yineleyici ilk Oluşturucusu oluşturur. İkinci ve üçüncü oluşturucular içinde Dizinim pval depolamak ve ardından açın ve dizin olarak Dizinim okuma girişimi. Başarılı olursa, ilk dosya adı myentry dizininde depoladıkları; Aksi takdirde bitiş dizisi yineleyici üretir.  
  
 Varsayılan construtors beklendiği gibi davranır.  
  
## <a name="directoryiteratorincrement"></a>directory_iterator::increment  
  
```  
directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 Sonraki filename dizininde ilerletmek işlevi çalışır. Başarılı olursa, o filename myentry içinde depolar; Aksi takdirde bitiş dizisi yineleyici üretir.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator! =  
  
```  
bool operator!=(const directory_iterator& right) const;
```  
  
 Üye işleci verir! (* Bu sağ ==).  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator =  
  
```  
directory_iterator& operator=(const directory_iterator&) = default;  
directory_iterator& operator=(directory_iterator&&) noexcept = default;  
```  
  
 Varsayılan üye atama işleçleri beklendiği gibi davranır.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator ==  
  
```  
bool operator==(const directory_iterator& right) const;
```  
  
 Üye işleci yalnızca her iki, true döndürür * bu ve bitiş dizisi yineleyiciler veya her ikisini de doğru olan değil end-in-sırası-yineleyiciler.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator *  
  
```  
const directory_entry& operator*() const;
```  
  
 Üye işleci myentry döndürür.  
  
## <a name="directoryiteratoroperator-"></a>directory_iterator::operator ->  
  
```  
const directory_entry * operator->() const;
```  
  
 Üye işlevi döndürür & ** Bu.  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator ++  
  
```  
directory_iterator& operator++();
directory_iterator& operator++(int);
```  
  
 İlk üye işlevi increment() çağırır ve ardından döndürür * bu. İkinci üye işlevi nesne bir kopyasını oluşturur, increment() çağırır ve ardından kopya döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<Deneysel/filesystem >  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<FileSystem >](../standard-library/filesystem.md)   
 [Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)

