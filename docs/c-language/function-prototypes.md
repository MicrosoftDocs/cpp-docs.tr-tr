---
title: İşlev Prototipleri
ms.date: 11/04/2016
helpviewer_keywords:
- function prototypes
- function return types, function prototypes
- data types [C], function return types
- functions [C], return types
- prototypes [C++], function
ms.assetid: d152f8e6-971e-432c-93ca-5a91400653c2
ms.openlocfilehash: 9c42ce5b23e6f755dafd57bdb5a5f79cf1adb4ec
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857092"
---
# <a name="function-prototypes"></a>İşlev Prototipleri

İşlev bildirimi, işlev tanımından önce gelir ve bir işlevin adını, dönüş türünü, depolama sınıfını ve diğer özniteliklerini belirtir. Prototip olması için, işlev bildiriminin işlevin bağımsız değişkenleri için türler ve tanımlayıcılar de kurması gerekir.

## <a name="syntax"></a>Sözdizimi

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *özniteliği-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub> **;**

/\* *özniteliği-seq*<sub>opt</sub> , Microsoft 'a özgü \*/

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *başlatıcısı*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*Direct-bildirimci*:/\* bir işlev bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**   / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

Prototip, kapatma parantezinden hemen sonra bir noktalı virgülle sonlandırıldığından ve bu nedenle gövde olmadığından, işlev tanımıyla aynı biçimde olur. Her iki durumda da, dönüş türü işlev tanımında belirtilen dönüş türüyle kabul etmelidir.

İşlev prototiplileri aşağıdaki önemli kullanımlarına sahiptir:

- Bunlar **int**dışında türler döndüren işlevler için dönüş türü oluştururlar. **İnt** değerleri döndüren işlevler Prototiplerde gerekli olmasa da, Prototiplerde önerilir.

- Tüm Prototiplerde, standart dönüştürmeler yapılır, ancak parametre sayısıyla bağımsız değişkenlerin türünü veya sayısını denetlemek için bir girişimde bulunuldu.

- Prototipler, işlevler tanımlanmadan önce işlevlere işaretçiler başlatmak için kullanılır.

- Parametre listesi, işlev çağrısındaki bağımsız değişkenlerin işlev tanımındaki parametrelerle yazışmaları denetlemek için kullanılır.

Her parametrenin dönüştürülmüş türü, işlev çağrısının yığına yerleştirdiği bağımsız değişkenlerin yorumlanmasını belirler. Bağımsız değişken ile bir parametre arasında tür uyuşmazlığı, yığındaki bağımsız değişkenlerin yanlış yorumlanmasına neden olabilir. Örneğin, 16 bit bir bilgisayarda, bir bağımsız değişken olarak bir 16 bit işaretçi geçirilirse ve **uzun** bir parametre olarak bildirilirse, yığındaki ilk 32 bit, **uzun** bir parametre olarak yorumlanır. Bu hata yalnızca **Long** parametresiyle değil, ancak bunu izleyen parametrelere sahip olan sorunları oluşturur. Tüm işlevler için tüm işlev prototiplerini bildirerek bu tür hataları tespit edebilirsiniz.

Bir prototip, bir işlevin özniteliklerini belirler, böylece tanımının önüne (veya diğer kaynak dosyalarında meydana gelen), bağımsız değişken türü ve dönüş türü uyuşmazlıkları için denetlenebilirler. Örneğin, bir prototip içinde **statik** depolama sınıfı Belirleyicisi belirtirseniz, işlev tanımında **statik** depolama sınıfını da belirtmeniz gerekir.

Tüm parametre bildirimleri (`int a`), aynı bildirimde soyut Bildirimciler (`int`) ile karışık olabilir. Örneğin, aşağıdaki bildirim geçerlidir:

```C
int add( int a, int );
```

Prototip, bağımsız değişken olarak geçirilen her bir ifade için hem türü hem de bir tanımlayıcı içerebilir. Ancak, bu tür tanımlayıcılara yalnızca bildirimin sonuna kadar kapsam vardır. Prototip Ayrıca, bağımsız değişken sayısının değişken olduğu veya hiçbir bağımsız değişken geçirilmeyeceği olguyu yansıtabilir. Bu tür bir liste olmadan, uyuşmazlıklar açığa çıkarmayabilir, bu nedenle derleyici bunlarla ilgili tanılama iletileri üretemiyor. Tür denetlemesi hakkında daha fazla bilgi için bkz. [bağımsız değişkenler](../c-language/arguments.md) .

Microsoft C derleyicisinde prototip kapsamı, **/za** derleyici seçeneği ile DERLERKEN artık ANSI uyumludur. Bu, bir prototip içinde bir **struct** veya **Union** etiketi bildirirseniz, etiketin genel kapsam yerine o kapsamda girildiğini gösterir. Örneğin, ANSI uyumluluğu için **/za** ile derlerken, bu işlevi bir tür uyumsuzluğu hatası vermeden hiçbir zaman Çağırmamanız gerekir:

```C
void func1( struct S * );
```

Kodunuzu düzeltmek için, işlev prototipiyle önce genel kapsamda **Yapı** veya **birleşim** tanımlayın veya bildirin:

```C
struct S;
void func1( struct S * );
```

**/Ze**altında, etiket hala genel kapsama girilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
