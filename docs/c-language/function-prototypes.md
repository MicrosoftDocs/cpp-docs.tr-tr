---
title: İşlev prototipleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function prototypes
- function return types, function prototypes
- data types [C], function return types
- functions [C], return types
- prototypes [C++], function
ms.assetid: d152f8e6-971e-432c-93ca-5a91400653c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6979bb90debc1734ccadf40b5d0e814d3c28c1ac
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="function-prototypes"></a>İşlev Prototipleri
Bir işlev bildirimi işlev tanımı önündeki ve adı, dönüş türü, depolama sınıfı ve diğer bir işlev özniteliklerini belirtir. Bir prototip olması için işlev bildirimi de türleri ve işlev bağımsız değişkenleri için tanımlayıcıları oluşturmanız gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
 `declaration`:  
 *bildirim tanımlayıcıları öznitelik-seq* kabul*init bildirimcisi listesi* kabul **;**  
  
 /\* *öznitelik seq* opt Microsoft Specific * /  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci bildirim tanımlayıcıları* iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları* iptal et  
  
 *Init bildirimcisi listesi*:  
 *Init bildirimcisi*  
  
 *Init bildirimcisi listesi***,***init bildirimcisi*  
  
 *Init bildirimcisi*:  
 *bildirimcisi*  
  
 *bildirimcisi Başlatıcı =*  
  
 `declarator`:  
 *İşaretçi* kabul*doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*: /\* işlevi bildirimcisi \*/  
 *doğrudan bildirimcisi***(***parametre türü listesi***)** / * yeni stil bildirimcisi \*/  
  
 *doğrudan bildirimcisi***(***tanımlayıcı listesi* kabul **)** / * Kullanımdan kalktı stili bildirimcisi \*/  
  
 Kapatma parantezi hemen ardından noktalı virgülle sonlandırılır ve bu nedenle hiçbir gövdesine sahip dışında prototip işlev tanımı olarak aynı biçime sahiptir. Her iki durumda da, dönüş türü bir işlev tanımında belirtilen dönüş türüyle kabul etmeniz gerekir.  
  
 İşlev prototipleri aşağıdaki önemli kullandığı vardır:  
  
-   Dönüş türleri dışındaki işlevler için dönüş türü kurmak `int`. İşlevler döndürür ancak `int` değerleri prototipleri gerekli olmadığı, prototipleri önerilir.  
  
-   Tam prototipleri olmadan standart dönüşümler yapılır, ancak türü veya sayıda bağımsız değişken parametre sayısı ile denetlemek için bir girişimde.  
  
-   Prototipler bu işlevlerin tanımlanmadan işlev işaretçileri başlatmak için kullanılır.  
  
-   Parametre listesi işlev çağrısı değişkenlerinde işlevi tanımında parametrelerle yazışmaları denetlemek için kullanılır.  
  
 Dönüştürülen her parametrenin türü, işlev çağrısı yığında yerleştirir bağımsız değişkenleri yorumu belirler. Bir bağımsız değişkeni bir parametre arasındaki bir tür uyuşmazlığı bağımsız değişkenleri yorumlanabileceğinden için yığın neden olabilir. Örneğin, 16-bit bir bilgisayarda bir 16 bit işaretçi bağımsız değişken olarak aktarılırsa, ardından bildirilen bir **uzun** parametresi, yığında ilk 32 bit olarak yorumlanır bir **uzun** parametresi. Sorun değil yalnızca bu hata oluşturur **uzun** parametresi, ancak izleyen herhangi bir parametre. Tüm İşlevler için tam işlev prototipleri bildirerek bu tür hatalarını algılayabilir.  
  
 Bir prototip bir işlev özniteliklerini oluşturur. böylece tanımına koyun (veya diğer kaynak dosyalarda meydana) işlev çağrıları bağımsız değişken türü ve dönüş türü uyuşmazlığı için denetlenebilir. Örneğin, belirtirseniz **statik** depolama sınıfı tanımlayıcısı prototip olarak da belirtmeniz gerekir **statik** işlevi tanımında depolama sınıfı.  
  
 Parametre bildirimleri tamamlayın (`int a`) ile soyut Bildirimciler karma (`int`) aynı bildirimi. Örneğin, aşağıdaki bildirimi uygundur:  
  
```  
int add( int a, int );  
```  
  
 Prototip türünü hem bağımsız değişken olarak geçirilen her deyim için bir tanımlayıcı içerebilir. Ancak, bu tür tanımlayıcıları yalnızca bildirimi sonuna kadar kapsama sahip. Prototip değişkenidir bağımsız değişken sayısı veya hiç bağımsız değişken geçirilir olgu da yansıtabilirsiniz. Derleyici bunları ilgili tanılama iletileri üretilemiyor böylece, böyle bir listeyi uyuşmazlıkları, açığa değil. Bkz: [bağımsız değişkenleri](../c-language/arguments.md) tür denetlemesi hakkında daha fazla bilgi.  
  
 Microsoft C Derleyici prototip kapsamda ANSI uyumlu /Za derleyici seçeneği ile derleme yapılırken sunulmuştur. Bunun anlamı bildirirseniz bir `struct` veya **UNION** bu kapsamda yerine genel kapsamlı bir prototip etiket etiket girilir. Örneğin, /Za ANSI uyumluluğu ile derleme yapılırken hiçbir zaman bu işlev bir tür uyuşmazlığı hatası almadan çağırabilirsiniz:  
  
```  
void func1( struct S * );  
```  
  
 Kodunuzu düzeltmek için tanımlayın veya bildirme `struct` veya **UNION** genel kapsamlı işlev prototipi önce:  
  
```  
struct S;  
void func1( struct S * );  
```  
  
 /Ze altında etiket hala genel kapsamda girilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../c-language/functions-c.md)