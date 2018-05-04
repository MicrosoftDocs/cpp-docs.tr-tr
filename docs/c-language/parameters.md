---
title: Parametreleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- function parameters
- parameters [C++]
- function arguments, vs. parameters
- parameters [C++], function
- functions [C], parameters
- function parameters, syntax
- ellipses (...), parameters
- '... ellipsis'
ms.assetid: 8f2b8026-78b5-4e21-86a3-bf0f91f05689
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 655cf3ac04385b055dfdf028261a2a61f3bb45f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="parameters"></a>Parametreler
Bağımsız değişkenler, bir işlev çağrısı tarafından bir işlevine geçirilen değerlerin adlardır. Parametreler işlev almak için bekliyor değerlerdir. Bir işlev prototipi işlevi adından parantez işlev parametrelerini ve türlerinin tam listesi içerir. Parametre bildirimleri türleri, boyutlar ve parametrelerinde depolanan değerlerin tanımlayıcıları belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
 *işlev tanımı*:  
 *bildirim tanımlayıcıları* kabul*özniteliği seq* kabul*bildirimcisi bildirimi listesi* kabul*bileşik deyim*  
  
 /\* *öznitelik seq* Microsoft Specific * /  
  
 *bildirimcisi* :  
 *İşaretçi* kabul*doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:/\* işlevi bildirimcisi \*/  
 *doğrudan bildirimcisi***(***parametre türü listesi***)** / * yeni stil bildirimcisi \*/  
  
 *parametre türü listesi*: /\* parametre listesi \*/  
 *parameter-list*  
  
 *parametre listesi***,...**  
  
 *parametre listesi*:  
 *parameter-declaration*  
  
 *parametre listesi***,***parametre bildirimi*   
  
 *parametre bildirimi*:  
 *bildirim tanımlayıcıları bildirimcisi*  
  
 *bildirim tanımlayıcıları Özet-bildirimcisi* iptal et  
  
 *Parametre türü listesi* parametre bildirimleri virgülle ayrılmış bir dizisidir. Parametre listesindeki her bir parametreyi form şöyle görünür:  
  
```  
[register]  type-specifier [declarator]   
```  
  
 İşlev parametreleri bildirilen ile **otomatik** özniteliği hataları oluşturun. Parametreleri tanımlayıcıların işlev gövdesine işlevine geçirilen değerleri başvurmak için kullanılır. Bir prototip parametrelerinde adlandırabilirsiniz, ancak bildirimi sonunda kapsam dışında adlarını gidin. Bu nedenle parametre adları aynı şekilde veya farklı işlevi tanımında atanabilir. İşlev gövdesi en dıştaki bloğunda tanımlayıcıları tanımlanamaz, ancak parametre listesi gibi davranarak kapsayan bir blok iç, iç içe geçmiş bloklarında tanımlanabilir.  
  
 Her tanımlayıcıda *parametre türü listesi* Bu örnekte gösterildiği gibi uygun bir tür tanımlayıcısı tarafından gelmelidir:  
  
```  
void new( double x, double y, double z )  
{  
    /* Function body here */  
}  
```  
  
 Parametre listesinde en az bir parametre meydana gelirse, listenin üç noktalarla ardından virgül ile sonlandırabilirsiniz (**,...** ). Değişken sayıda bağımsız değişken işlevine "üç nokta gösterimi," olarak adlandırılan bu yapım gösterir. (Bkz [bir değişken sayısı değişkenlerin aramaları](../c-language/calls-with-a-variable-number-of-arguments.md) daha fazla bilgi için.) Bununla birlikte, işlevi çağrısı son virgülle önce parametrelerin olarak en az sayıda bağımsız değişken olmalıdır.  
  
 İşlev için geçirilecek bağımsız değişkenler varsa, parametrelerin listesi anahtar sözcüğüyle değiştirilir `void`. Bu kullanımını `void` tür belirteci olarak kullanılmasını farklıdır.  
  
 Sipariş ve üç nokta gösterimi, herhangi bir kullanımından dahil parametreleri türünü (varsa) ilgili tüm işlev bildirimleri ve işlev tanımının'de aynı olması gerekir. Olağan aritmetik dönüştürmeler atama uyumlu olmalıdır sonra bağımsız değişken türleri ile ilgili parametreleri türleri. (Bkz [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) aritmetik dönüşümler hakkında bilgi için.) Üç nokta aşağıdaki değişkenleri denetlenmez. Bir parametre yapısı, UNION, işaretçi herhangi temel sahip veya dizi türü.  
  
 Derleyici olağan aritmetik dönüştürmeler bağımsız olarak her bir parametreyi ve her bağımsız gerekirse gerçekleştirir. Hiçbir parametre dönüştürmeden sonra daha kısa bir `int`, ve bir parametre yok **float** parametre türü olarak açıkça belirtilmediği sürece yazın **float** prototip içinde. Bu, örneğin, bu parametre olarak bildirme anlamına gelir bir `char` olarak bildirme aynı etkiye sahip bir `int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C İşlev Tanımları](../c-language/c-function-definitions.md)