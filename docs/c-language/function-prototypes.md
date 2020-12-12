---
description: 'Daha fazla bilgi edinin: Işlev prototipleri'
title: İşlev Prototipleri
ms.date: 11/04/2016
helpviewer_keywords:
- function prototypes
- function return types, function prototypes
- data types [C], function return types
- functions [C], return types
- prototypes [C++], function
ms.assetid: d152f8e6-971e-432c-93ca-5a91400653c2
ms.openlocfilehash: d8e83e68daaa610387f3a23c06ad5ee49a8b3944
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151846"
---
# <a name="function-prototypes"></a>İşlev Prototipleri

İşlev bildirimi, işlev tanımından önce gelir ve bir işlevin adını, dönüş türünü, depolama sınıfını ve diğer özniteliklerini belirtir. Prototip olması için, işlev bildiriminin işlevin bağımsız değişkenleri için türler ve tanımlayıcılar de kurması gerekir.

## <a name="syntax"></a>Syntax

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-tanımlayıcılar* *özniteliği-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub> **;**

/\**öznitelik-Seq*<sub>opt</sub> , Microsoft 'a özgü\*/

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list*  **,**  *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *Başlatıcı*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*Direct-bildirimci*:/ \* bir işlev bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-bildirimci***(***parametre türü-liste***)**   / \* Yeni stil bildirimci      \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-bildirimci***(***tanımlayıcı listesi*<sub>opt</sub> **)**  / \* eski stil bildirimci    \*/

Prototip, kapatma parantezinden hemen sonra bir noktalı virgülle sonlandırıldığından ve bu nedenle gövde olmadığından, işlev tanımıyla aynı biçimde olur. Her iki durumda da, dönüş türü işlev tanımında belirtilen dönüş türüyle kabul etmelidir.

İşlev prototiplileri aşağıdaki önemli kullanımlarına sahiptir:

- Bunlar dışındaki türleri döndüren işlevler için dönüş türü oluştururlar **`int`** . Değer döndüren işlevler **`int`** prototipler gerektirmese de Prototiplerde önerilir.

- Tüm Prototiplerde, standart dönüştürmeler yapılır, ancak parametre sayısıyla bağımsız değişkenlerin türünü veya sayısını denetlemek için bir girişimde bulunuldu.

- Prototipler, işlevler tanımlanmadan önce işlevlere işaretçiler başlatmak için kullanılır.

- Parametre listesi, işlev çağrısındaki bağımsız değişkenlerin işlev tanımındaki parametrelerle yazışmaları denetlemek için kullanılır.

Her parametrenin dönüştürülmüş türü, işlev çağrısının yığına yerleştirdiği bağımsız değişkenlerin yorumlanmasını belirler. Bağımsız değişken ile bir parametre arasında tür uyuşmazlığı, yığındaki bağımsız değişkenlerin yanlış yorumlanmasına neden olabilir. Örneğin, 16 bit bir bilgisayarda, bir bağımsız değişken olarak bir 16 bit işaretçi geçirilirse ve sonra parametre olarak bildirilirse **`long`** , yığındaki ilk 32 bit bir parametre olarak yorumlanır **`long`** . Bu hata **`long`** , yalnızca parametresiyle değil, ancak bunu izleyen parametrelere sahip olan sorunları oluşturur. Tüm işlevler için tüm işlev prototiplerini bildirerek bu tür hataları tespit edebilirsiniz.

Bir prototip, bir işlevin özniteliklerini belirler, böylece tanımının önüne (veya diğer kaynak dosyalarında meydana gelen), bağımsız değişken türü ve dönüş türü uyuşmazlıkları için denetlenebilirler. Örneğin, **`static`** bir prototipde depolama sınıfı Belirleyicisi belirtirseniz, **`static`** işlev tanımında depolama sınıfını da belirtmeniz gerekir.

Tüm parametre bildirimleri ( `int a` ), aynı bildirimde soyut Bildirimciler () ile karışık olabilir **`int`** . Örneğin, aşağıdaki bildirim geçerlidir:

```C
int add( int a, int );
```

Prototip, bağımsız değişken olarak geçirilen her bir ifade için hem türü hem de bir tanımlayıcı içerebilir. Ancak, bu tür tanımlayıcılara yalnızca bildirimin sonuna kadar kapsam vardır. Prototip Ayrıca, bağımsız değişken sayısının değişken olduğu veya hiçbir bağımsız değişken geçirilmeyeceği olguyu yansıtabilir. Bu tür bir liste olmadan, uyuşmazlıklar açığa çıkarmayabilir, bu nedenle derleyici bunlarla ilgili tanılama iletileri üretemiyor. Tür denetlemesi hakkında daha fazla bilgi için bkz. [bağımsız değişkenler](../c-language/arguments.md) .

Microsoft C derleyicisinde prototip kapsamı, **/za** derleyici seçeneği ile DERLERKEN artık ANSI uyumludur. Yani **`struct`** **`union`** , bir prototip içinde bir veya etiketi bildirirseniz, etiketin genel kapsam yerine o kapsamda girildiği anlamına gelir. Örneğin, ANSI uyumluluğu için **/za** ile derlerken, bu işlevi bir tür uyumsuzluğu hatası vermeden hiçbir zaman Çağırmamanız gerekir:

```C
void func1( struct S * );
```

Kodunuzu düzeltmek için, **`struct`** **`union`** işlev prototipten önce veya genel kapsamını tanımlayın veya bildirin:

```C
struct S;
void func1( struct S * );
```

**/Ze** altında, etiket hala genel kapsama girilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
