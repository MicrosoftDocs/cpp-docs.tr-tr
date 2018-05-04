---
title: Bildirimlere genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, about declarations
- type qualifiers
ms.assetid: fcd2364c-c2a5-4fbf-9027-19dac4144cb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd8670815b908f66a6e2ed400bc87ca07c369ee4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="overview-of-declarations"></a>Bildirimlere Genel Bakış
"Bildirim" yorumunu ve tanımlayıcıları Kümesi özniteliklerini belirtir. Ayrıca nesne veya tanımlayıcısıyla adlı işlev için ayrılmış depolama neden olan bir bildirimi "tanımı." olarak adlandırılır Değişkenler, İşlevler ve türler için C bildirimleri bu sözdizimine sahip:  
  
## <a name="syntax"></a>Sözdizimi  
 `declaration`:  
 *bildirim tanımlayıcıları* *özniteliği seq*kabul*init bildirimcisi listesi*kabul **;**  
  
 /\* *öznitelik seq*opt Microsoft özeldir * /  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları*iptal et  
  
 *tür belirteci bildirim tanımlayıcıları*iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları*iptal et  
  
 *Init bildirimcisi listesi*:  
 *Init bildirimcisi*  
  
 *Init bildirimcisi listesi* , *init bildirimcisi*  
  
 *Init bildirimcisi*:  
 *bildirimcisi*  
  
 *bildirimcisi***=***Başlatıcı*  
  
> [!NOTE]
>  Bu sözdiziminin `declaration` aşağıdaki bölümlerde yinelenmez. Aşağıdaki bölümlerde sözdizimi genellikle başlıyorsa `declarator` nonterminal.  
  
 Bildirimler *init bildirimcisi listesi* adın geçmesi; tanımlayıcıları içerir *init* Başlatıcısı ifadesinin kısaltmasıdır. *İnit bildirimcisi listesi* her biri olabilir ek tür bilgileri veya bir başlatıcı ya da her ikisini de Bildirimciler, virgülle ayrılmış bir dizisidir. `declarator` Varsa bildirilen tanımlayıcıları içerir. *Bildirim tanımlayıcıları* nonterminal belirtmek depolama süresi, bağlantı türü ve depolama sınıfı tanımlayıcıları dizisini oluşur ve en az bir parçası Bildirimciler belirtmek varlık türü. Bu nedenle, bildirimleri depolama sınıfı tanımlayıcıları, tür tanımlayıcıları, tür niteleyicileri, bildirimler ve başlatıcılar bazı birleşiminden oluşur.  
  
 Bildirimleri bir içerebilir veya daha fazla isteğe bağlı öznitelik listelenen *özniteliği seq*; *seq* dizisi ifadesinin kısaltmasıdır. Microsoft'a özgü özniteliklerden çeşitli bu kitap boyunca ayrıntılı ele alınmıştır işlevler gerçekleştirir.  
  
 Bir değişken bildirimi genel biçiminde *tür belirteci* değişkeninin veri türü sağlar. *Tür belirteci* türü tarafından zaman değişiklik olarak bir bileşik olabilir **const** veya `volatile`. `declarator` Bir dizi veya bir işaretçi türü bildirmek için büyük olasılıkla değiştirilmiş değişkeninin adı sağlar. Örneğin,  
  
```  
int const *fp;  
```  
  
 adlı bir değişken bildiren `fp` gösteren bir işaretçi bir değiştirilemez olarak (**const**) `int` değeri. Virgülle ayırarak, birden çok Bildirimciler kullanarak bir bildiriminde birden fazla değişken tanımlayabilirsiniz.  
  
 Bir bildirim en az bir bildirimcisi sahip olmalı veya tür belirleyici bir yapı etiketi, birleşim etiketi veya numaralandırma üyeleri bildirmeniz gerekir. Bildirimciler kalan herhangi bir tanımlayıcı bilgilerini sağlayın. Bir bildirimcisi köşeli parantez ile değiştirilebilir bir tanımlayıcıdır (**[]**), yıldız işareti (**\***), ya da parantez ( **()** ) bir diziyi bildirmek için işaretçisi veya işlev türü, sırasıyla. (Örneğin, karakter, tamsayı ve kayan nokta öğeleri), basit değişkenler veya yapılar ve birleşimleri basit değişkenlerin bildirirken `declarator` yalnızca bir tanımlayıcıdır. Bildirimciler hakkında daha fazla bilgi için bkz: [bildirimler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md).  
  
 Tüm tanımları örtük olarak bildirimleri, ancak tüm bildirimleri tanımlar. Örneğin, ile başlayan değişken bildirimleri `extern` depolama sınıfı tanımlayıcısı "başvuran," yerine "tanımlama" bildirimler. Bir dış değişken tanımlanmadan önce başvurulan ise ya da başka bir kaynak dosyasında bir nereden kullanıldığı, tanımlanırsa, bir `extern` bildirimi gereklidir. Depolama "bildirimler başvurarak" alınmaz veya değişkenleri bildirimlerinde başlatılabilir.  
  
 Depolama sınıfı ya da bir türü (veya her ikisi de) değişken bildirimlerinde gereklidir. Dışında `__declspec`, yalnızca bir depolama sınıfı tanımlayıcısı bir bildiriminde izin verilir ve tüm depolama sınıfı tanımlayıcıları her bağlamında izin verilir. `__declspec` Depolama sınıfı, diğer depolama sınıfı tanımlayıcıları ile verilir ve birden çok kez izin verilir. Depolama sınıfı tanımlayıcısı bir bildirim bildirilen öğesi nasıl depolandığını ve başlatıldı ve hangi kısımlarının bir program öğesi başvurusu yapabilir etkiler.  
  
 *Depolama sınıfı tanımlayıcısı* C'de tanımlanan Terminal dahil **otomatik**, `extern`, **kaydetmek**, **statik**ve `typedef`. Ayrıca, Microsoft C içeren *depolama sınıfı tanımlayıcısı* terminal `__declspec`. Tüm *depolama sınıfı tanımlayıcısı* dışında Terminal `typedef` ve `__declspec` ele alınmıştır [depolama sınıfları](../c-language/c-storage-classes.md). Bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md) hakkında bilgi için `typedef`. Bkz: [genişletilmiş depolama sınıfı öznitelikler](../c-language/c-extended-storage-class-attributes.md) hakkında bilgi için `__declspec`.  
  
 Kaynak program ve durum bildirimi konumunu veya diğer bildirimleri değişkenin yokluğu değişkenleri ömrü belirlemede önemli faktörler olan. Birden çok redeclarations ancak yalnızca tek bir tanım olabilir. Ancak, bir tanım birden fazla çeviri biriminde yer alabilir. Dahili olarak bağlantılı nesneler bir çeviri birimine benzersiz olduğundan iç bağlantı nesneleri için bu kural her çeviri birim için ayrı olarak uygulanır. Dış bağlantılı nesneler için bu kural tüm programına uygular. Bkz: [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) görünürlük hakkında daha fazla bilgi.  
  
 Tür tanımlayıcıları tanımlayıcıları veri türleri hakkında bazı bilgiler sağlar. Varsayılan tür belirleyici olduğu `int`. Daha fazla bilgi için bkz: [tür tanımlayıcıları](../c-language/c-type-specifiers.md). Tür tanımlayıcıları da türü etiketleri, yapı ve birleşim bileşen adlarına ve numaralandırma sabitleri tanımlayabilirsiniz. Daha fazla bilgi için bkz: [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md), [yapı bildirimleri](../c-language/structure-declarations.md), ve [birleşim bildirimleri](../c-language/union-declarations.md).  
  
 Var olan iki *tür niteleyicisi* Terminal: **const** ve `volatile`. Bu niteleyiciler yalnızca bu tür nesneleri l değerleri erişirken ilgili türlerin ek özellikleri belirtin. Daha fazla bilgi için **const** ve `volatile`, bkz: [tür niteleyicileri](../c-language/type-qualifiers.md). L değerleri tanımı için bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md)   
 [Bildirimler ve türler](../c-language/declarations-and-types.md)   
 [Bildirimlerin Özeti](../c-language/summary-of-declarations.md)