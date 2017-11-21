---
title: '&lt;iOS&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <ios>
- ios/std::<ios>
dev_langs: C++
helpviewer_keywords: ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04992f8324196c5fd762ba01a96fff7cc6ba6539
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltiosgt"></a>&lt;iOS&gt;
İostreams işlemi için çeşitli türleri ve temel işlevleri tanımlar. Bu üst başka bir iostream üstbilgileri tarafından sizin için genellikle bulunur; nadiren doğrudan dahil.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <ios>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çok sayıda işlevleri manipülatörleri var. Bir manipulator bildirilen \<ios > sınıfının bağımsız değişken nesnesinde depolanan değerleri değiştirir [ios_base](../standard-library/ios-base-class.md). Diğer manipülatörleri şablon sınıfları birini uzmanlaşması gibi bu sınıftan türetilen türdeki nesneleri tarafından denetlenen akışları eylemler gerçekleştirme [basic_istream](../standard-library/basic-istream-class.md) veya [basic_ostream](../standard-library/basic-ostream-class.md). Örneğin, [noskipws](../standard-library/ios-functions.md#noskipws)(**str**) biçimi bayrağını temizler `ios_base::skipws` nesnesindeki **str**, olabilen bu türlerden biri.  
  
 Ayrıca, bir çıkış akışı ekleyerek bir manipulator çağırabilirsiniz veya sınıflar için sağlanan özel ekleme ve çıkarma işlemleri nedeniyle bir giriş akıştan ayıklanıyor türetilen `ios_base`. Örneğin:  
  
```
istr>> noskipws;
```  
  
 çağrıları [noskipws](../standard-library/ios-functions.md#noskipws)(**istr**).  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[iOS](../standard-library/ios-typedefs.md#ios)|Eski iostream kitaplığı ios sınıfından destekler.|  
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|İç işlemleri destekler.|  
|[streampos](../standard-library/ios-typedefs.md#streampos)|Arabellek işaretçi veya dosya işaretçisini geçerli konumunu tutar.|  
|[streamsize](../standard-library/ios-typedefs.md#streamsize)|Akış boyutunu belirtir.|  
|[wios](../standard-library/ios-typedefs.md#wios)|Eski iostream kitaplığı wios sınıfından destekler.|  
|[wstreampos](../standard-library/ios-typedefs.md#wstreampos)|Arabellek işaretçi veya dosya işaretçisini geçerli konumunu tutar.|  
  
### <a name="manipulators"></a>Manipülatörleri  
  
|||  
|-|-|  
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|Belirtir türündeki bu değişkenler [bool](../cpp/bool-cpp.md) olarak görünür **true** veya **false** akış.|  
|[Ara](../standard-library/ios-functions.md#dec)|Tamsayı değişkenleri temel 10 gösterimde görüntüleneceğini belirtir.|  
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|Bayraklarını yapılandırır bir `ios_base` nesne float değerleri için bir varsayılan görüntü biçimi kullanın.|  
|[Sabit](../standard-library/ios-functions.md#fixed)|Bir kayan noktalı sayının Sabit ondalık gösterimde görüntüleneceğini belirtir.|  
|[onaltılık](../standard-library/ios-functions.md#hex)|Tamsayı değişkenleri temel 16 gösterimde görüntüleneceğini belirtir.|  
|[İç](../standard-library/ios-functions.md#internal)|Sayının işaretini sola hizalı olarak ve sağa hizalı olarak numarası neden olur.|  
|[Sol](../standard-library/ios-functions.md#left)|Sol kenar boşluğu ile akış temizleme görünmesi çıkış genişliği kadar geniş değil metin neden olur.|  
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|Belirtir türündeki bu değişkenler [bool](../cpp/bool-cpp.md) 1 veya 0'a akış olarak görünür.|  
|[noshowbase](../standard-library/ios-functions.md#noshowbase)|Bir sayı görüntülendiği notational temel belirten devre dışı bırakır.|  
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|Kayan nokta sayıları, kesirli bölümü sıfırdır yalnızca tam sayı bölümünü görüntüler.|  
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|Açıkça imzalanmamış pozitif sayılar neden olur.|  
|[noskipws](../standard-library/ios-functions.md#noskipws)|Giriş akışı tarafından okunacak alanları neden.|  
|[nounitbuf](../standard-library/ios-functions.md#nounitbuf)|Çıkış arabelleğe ve arabellek dolduğunda, işlenen için neden olur.|  
|[nouppercase](../standard-library/ios-functions.md#nouppercase)|Onaltılık basamak ve bilimsel gösterimde üs küçük harflerle görüntüleneceğini belirtir.|  
|[Eki](../standard-library/ios-functions.md#oct)|Tamsayı değişkenleri temel 8 gösterimde görüntüleneceğini belirtir.|  
|[sağ](../standard-library/ios-functions.md#right)|Sağ kenar boşluğu ile akış temizleme görünmesi çıkış genişliği kadar geniş değil metin neden olur.|  
|[Bilimsel](../standard-library/ios-functions.md#scientific)|Kayan nokta numarası bilimsel gösterim kullanılarak görüntülenmesine neden olur.|  
|[showbase](../standard-library/ios-functions.md#showbase)|Bir sayı görüntülendiği notational temel gösterir.|  
|[showpoint](../standard-library/ios-functions.md#showpoint)|Kesirli bölümü sıfır olsa bile bir kayan noktalı sayı ve basamak tamsayılı bölümünü ondalık konumun sağında görüntüler.|  
|[showpos](../standard-library/ios-functions.md#showpos)|Açıkça imzalanacak pozitif sayılar neden olur.|  
|[skipws](../standard-library/ios-functions.md#skipws)|Giriş akışı tarafından değil okunacak alanları neden.|  
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|Çıkış arabelleği boş olmadığında işlenmesi için neden olur.|  
|[büyük harf](../standard-library/ios-functions.md#uppercase)|Onaltılık basamak ve bilimsel gösterimde üs büyük görüntüleneceğini belirtir.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[basic_ios](../standard-library/basic-ios-class.md)|Şablon sınıfı için her iki giriş akışları ortak depolama ve üye işlevleri açıklanmaktadır (şablon sınıfının [basic_istream](../standard-library/basic-istream-class.md)) ve çıkış akışları (şablon sınıfının [basic_ostream](../standard-library/basic-ostream-class.md)), bağlıdır Şablon parametreleri.|  
|[fpos](../standard-library/fpos-class.md)|Şablon sınıfı bir rastgele dosya konumu göstergesi akış içinde geri yüklemek için gerekli tüm bilgileri depolayan bir nesne tanımlar.|  
|[ios_base](../standard-library/ios-base-class.md)|Şablon parametreleri dayanmayan ortak giriş ve çıkış akışları üye işlevleri ve depolama sınıfı açıklanmaktadır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)



