---
title: '&lt;dosya sistemi&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
dev_langs: C++
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c8e09c494ee23d227321a807c8c533d16f981a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltfilesystemgt"></a>&lt;dosya sistemi&gt;
Üstbilgisini &lt;filesystem > erişim sınıfları ve işlevleri yönetmek ve yolları, dosyalar ve dizinler hakkında bilgi almak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
#include <experimental/filesystem> // C++-standard header file name  
#include <filesystem> // Microsoft-specific implementation header file name  
using namespace std::experimental::filesystem::v1;  
```  
  
> [!IMPORTANT]
>  Visual Studio 2017 sürümü itibariyle \<filesystem > üstbilgisi değil henüz C++ standart. Visual C++ 2017 uygulayan son taslak standart, bulunan [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf).  
  
 Bu üst bağlanan dosya sistemlerinin bir ana bilgisayar işletim sistemlerinin iki geniş sınıfların destekler: Microsoft Windows ve POSIX.  
  
 En iyi işlevselliği her iki işletim sistemleri için ortak olsa da, bu belgede farklar gerçekleştiği tanımlar. Örneğin:  
  
-   Windows c: gibi birden çok kök adlarını destekler veya \\\network_name. Bir orman ağaçları, her c:\ gibi kendi kök dizinine sahip bir dosya sistemi oluşur veya \\\network_name\\ve her bir göreli yol (bir mutlak bir yol adı değil) tamamlamak için kendi geçerli dizini.  
  
-   POSIX destekleyen kök adı, tek bir kök dizin olmayan tek bir ağaç / ve tek bir geçerli dizin.  
  
 Başka bir önemli fark, yerel yol adları gösterimidir:  
  
-   Windows, UTF-16 (her karakter için bir veya iki öğe) olarak kodlanmış wchar_t null ile sonlandırılmış bir dizi kullanır.  
  
-   POSIX UTF-8 (her bir karakteri için bir veya daha fazla öğeleri) olarak kodlanmış karakter null ile sonlandırılmış bir dizi kullanır.  
  
-   Bir nesne sınıfı yolunun yol yerel biçiminde depolar, ancak bu arasında destekler kolay dönüştürme formu ve birkaç dış formları depolanan:  
  
-   İşletim sistemi tarafından ayrıcalıklı olarak kodlanmış karakter null ile sonlandırılmış dizisi.  
  
-   UTF-8 olarak kodlanmış karakter null ile sonlandırılmış dizisi.  
  
-   İşletim sistemi tarafından ayrıcalıklı olarak kodlanmış wchar_t null ile sonlandırılmış dizisi.  
  
-   UTF-16 kodlanmış char16_t null ile sonlandırılmış dizisi.  
  
-   UTF-32 kodlanmış char32_t null ile sonlandırılmış dizisi.  
  
 İşbu Beyanları arasında interconversions mediated, gerektiğinde bir veya daha fazla kullanımıyla `codecvt` yönü. Bir özel yerel ayara nesnesi belirlenmemişse, bu yönleri genel yerel ayarını elde edilir.  
  
 Başka bir fark ile her işletim sistemi dosya veya dizin erişim izinleri tanımlamalarına olanak sağlayan ayrıntısı şöyle:  
  
1.  Windows kayıt yalnızca veya yazılabilir bir dosyayı okuma olup, dizinler için hiçbir anlamı sahip bir öznitelik.  
  
2.  POSIX dosya, (bir dizin, taranan), yazılan ya da yürütülen okunup okunamayacağını sahibi, sahibin grubu veya herkes artı birkaç diğer izinler tarafından kaydeder.  
  
 Kök adı aldıktan sonra her iki sistemle ortak yapısı üzerinde pathname sınırlamasıdır. Pathname c:/abc/xyz/def.ext için:  
  
-   Kök c: adıdır.  
  
-   Kök dizini /.  
  
-   Kök yolu c: olduğu /.  
  
-   Göreli abc/xyz/def.ext yoludur.  
  
-   C:/abc/xyz üst yoludur.  
  
-   Dosya def.ext adıdır.  
  
-   Def stem olduğu  
  
-   Uzantısıdır. dahili  
  
 İkincil bir farktır **tercih edilen ayırıcı**, arasında bir pathname dizinlerde dizisi. Her iki işletim sistemi eğik yazmanıza izin /, ancak bazı bağlamlarda Windows bir ters eğik çizgi tercih \\.  
  
 Son olarak, bir önemli yol nesneleri üstbilgisinde tanımlanan sınıfların bir dosya adı bağımsız değişkeni gerekli olduğunda, bunları kullanabileceğiniz özelliğidir \<fstream >.  
  
 Daha fazla bilgi ve kod örnekleri için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[directory_entry Sınıfı](../standard-library/directory-entry-class.md)|Tarafından döndürülen bir nesneyi tanımlayan bir `directory_iterator` veya `recursive_directory_iterator` ve bir yol içeriyor.|  
|[directory_iterator Sınıfı](../standard-library/directory-iterator-class.md)|Bir dosya sistemi dizinde dosya adlarının aracılığıyla dizilerinin giriş yineleyici açıklar.|  
|[filesystem_error Sınıfı](../standard-library/filesystem-error-class.md)|Bir alt düzey sistem taşması bildirmek için oluşturulan özel durumlar için temel sınıf.|  
|[path Sınıfı](../standard-library/path-class.md)|Şablon türünde bir nesne depolar bir sınıfı tanımlar `String` bir dosya adı olarak kullanmaya uygun olmasıdır.|  
|[recursive_directory_iterator Sınıfı](../standard-library/recursive-directory-iterator-class.md)|Bir dosya sistemi dizinde dosya adlarının aracılığıyla dizilerinin giriş yineleyici açıklar. Yineleyici içinde alt dizinler de düzen.|  
|[file_status Sınıfı](../standard-library/file-status-class.md)|Saran bir `file_type`.|  
  
## <a name="structs"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[space_info Yapısı](../standard-library/space-info-structure.md)|Bir birim ilgili bilgileri tutar.|  
  
## <a name="functions"></a>İşlevler  
 [\<FileSystem > işlevleri](../standard-library/filesystem-functions.md)  
  
## <a name="operators"></a>İşleçler  
 [\<FileSystem > işleçleri](../standard-library/filesystem-operators.md)  
  
## <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|İle birlikte kullanılan bir numaralandırma [copy_file](http://msdn.microsoft.com/4af7a9b0-8861-45ed-b84e-0307f0669d60) ve hedef dosya zaten mevcutsa davranışını belirler.|  
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|Dizin yineleyiciler seçeneklerini belirten numaralandırması.|  
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|Dosya türleri için numaralandırması.|  
|[izinleri](../standard-library/filesystem-enumerations.md#perms)|İzinler ve izinleri seçenekleri iletmek için kullanılan bir bit maskesi türü|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)



