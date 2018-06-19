---
title: C depolama sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- static variables, lifetime
- storage classes
- lifetime, variables
- specifiers, storage class
- storage class specifiers, C storage classes
- storage duration
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 089f2298cac21ac9fff0d25a76e9393cddb84bba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386076"
---
# <a name="c-storage-classes"></a>C Depolama Sınıfları
Bir değişkenin "depolama sınıfı" öğesi "Genel" veya "yerel" ömrü olup olmadığını belirler. C "statik" ve "Otomatik" Bu iki yaşam süresi'ı çağırır Genel bir ömre sahip bir öğe var ve programın yürütülmesi boyunca bir değere sahip. Tüm işlevleri genel ömürleri vardır.  
  
 Otomatik değişkenler ya da yerel ömürleri değişkenlerle her zaman yürütme denetim geçirir bloğuna yeni depolama ayrılır içinde bunlar tanımlanır. Yürütme geri döndüğünde, değişkenleri artık anlamlı değerlere sahiptir.  
  
 C aşağıdaki depolama sınıfı tanımlayıcıları sağlar:  
  
## <a name="syntax"></a>Sözdizimi  
 *depolama sınıfı tanımlayıcısı*:  
 **auto**  
  
 **Kaydetme**  
  
 **static**  
  
 **extern**  
  
 **TypeDef**  
  
 **__declspec** ( *genişletilmiş-decl-değiştirici-seq* ) / * Microsoft Specific \*/  
  
 Dışında `__declspec`, yalnızca birini kullanabilir *depolama sınıfı tanımlayıcısı* içinde *bildirimi belirleyici* bir bildirimi. Depolama sınıfı belirtime yaptıysanız, bir blok bildirimlerinde otomatik nesneleri oluşturma.  
  
 Öğeleri bildirilen ile **otomatik** veya **kaydetmek** belirticisi yerel yaşam süresi vardır. Öğeleri bildirilen ile **statik** veya `extern` belirticisi genel yaşam süresi vardır.  
  
 Bu yana `typedef` ve `__declspec` diğer dört anlamsal olarak farklı *depolama sınıfı tanımlayıcısı* Terminal, ayrı ayrı ele alınmıştır. Belirli bilgileri için `typedef`, bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md). Belirli bilgileri için `__declspec`, bkz: [genişletilmiş depolama sınıfı öznitelikler](../c-language/c-extended-storage-class-attributes.md).  
  
 Kaynak dosyaları değişkeni ve işlev bildirimlerinde yerleşimini de depolama sınıfı ve görünürlük etkiler. Tüm işlev tanımları dışında bildirimleri "dış düzeyinde." görünen söylenir İşlev tanımları bildirimlerinde "İç düzeyinde." görüntülenir  
  
 Her depolama sınıfı tanımlayıcısı tam anlamını iki etkenlere bağlıdır:  
  
-   Bildirim harici veya dahili düzeyinde görünüp görünmeyeceğini belirtir  
  
-   Bildirilen öğe bir değişken veya işlev olup  
  
 [Dış düzey bildirimleri depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-for-external-level-declarations.md) ve [iç düzey bildirimleri depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-for-internal-level-declarations.md) açıklayan *depolama sınıfı tanımlayıcısı* Terminal içinde her tür bildirimi ve varsayılan davranışı açıklamak olduğunda *depolama sınıfı tanımlayıcısı* bir değişkeninden atlanır. [İşlev bildirimli depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-with-function-declarations.md) işlevleri ile kullanılan depolama sınıfı tanımlayıcıları açıklanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Türler](../c-language/declarations-and-types.md)