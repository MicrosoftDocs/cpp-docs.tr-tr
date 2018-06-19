---
title: Depolama sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecd50ddf72fbafb23571e2b2709418e4eb89093e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391437"
---
# <a name="storage-class"></a>Depolama Sınıfı
Depolama sınıfı tanımlayıcısı işlevi tanımında işlev ya da verir `extern` veya **statik** depolama sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
 *işlev tanımı*:  
 *bildirim tanımlayıcıları* kabul*özniteliği seq* kabul*bildirimcisi bildirimi listesi* kabul*bileşik deyim*  
  
 /\* *öznitelik seq* Microsoft Specific * /  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci bildirim tanımlayıcıları* iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları* iptal et  
  
 *depolama sınıfı tanımlayıcısı*: /\* işlev tanımları \*/  
 **extern**  
  
 **static**  
  
 Bir işlev tanımı içermiyorsa bir *depolama sınıfı tanımlayıcısı*, depolama sınıfı varsayılanları `extern`. Bir işlevi açıkça `extern` olarak bildirebilirsiniz, ancak bu gerekli değildir.  
  
 Bir işlevin bildirimi içeriyorsa *depolama sınıfı tanımlayıcısı* `extern`, dosya kapsamı tanımlayıcısıyla görünür herhangi bildirimi olarak aynı bağlantı tanımlayıcısı vardır. Dosya kapsamına sahip görünür bir bildirim yoksa, tanımlayıcının dış bağlantısı vardır. Dosya kapsamı ve Hayır bir tanımlayıcı olup olmadığını *depolama sınıfı tanımlayıcısı*, dış bağlantı tanımlayıcısı vardır. Dış bağlantı, tanımlayıcının her örneğinin aynı nesneyi veya işlevi gösterdiği anlamına gelir. Bkz: [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) bağlantı ve dosya kapsamı hakkında daha fazla bilgi için.  
  
 `extern` dışında depolama sınıfı tanımlayıcısına sahip blok kapsamı işlev bildirimleri hata oluşturur.  
  
 Bir işlev **statik** depolama sınıfı tanımlanmış yalnızca kaynak dosyasında görülebilir. Diğer tüm işlevler, ister açıkça ister örtük olarak `extern` depolama sınıfı verilsin, programdaki tüm kaynak dosyalarında görülür. Varsa **statik** depolama sınıfı istenen, bu işlevin bildirimi (varsa) ilk örneğini ve işlevinin tanımı bildirilmelidir.  
  
 **Microsoft özel**  
  
 Microsoft uzantıları etkinleştirildiğinde, bir işlevi olarak bildirilen depolama sınıfı (veya ile `extern` depolama sınıfı) verilen **statik** işlev tanımı aynı kaynak dosyasına açıksa ve durumdaysa depolama sınıfı tanımını açıkça belirtir **statik** depolama sınıfı.  
  
 /Ze derleyici seçeneğiyle derleme yapılırken, `extern` anahtar sözcüğü kullanılarak bir blok içerisinde bildirilen işlevlerin genel görünürlüğü olur. Bu, /Za ile derleme yapılırken doğru değildir. Kaynak kodunun taşınabilirliği önemliyse, bu özelliğe bağlı kalınmamalıdır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C İşlev Tanımları](../c-language/c-function-definitions.md)