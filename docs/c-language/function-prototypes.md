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
ms.openlocfilehash: 2c75db3e1550927af57054a2cc1561d9df1567a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233144"
---
# <a name="function-prototypes"></a>İşlev Prototipleri

Bir işlev bildirimi işlev tanımı önündeki ve adı, dönüş türü, depolama sınıfı ve diğer öznitelikleri bir işlevi belirtir. Bir prototip olması için işlev bildirimi de türleri ve işlev bağımsız tanımlayıcıları oluşturmanız gerekir.

## <a name="syntax"></a>Sözdizimi

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *öznitelik-seq*<sub>iyileştirilmiş</sub> *init-declarator-list*<sub>iyileştirilmiş</sub> **;**

/\* *öznitelik-seq*<sub>iyileştirilmiş</sub> Microsoft Specific \*/

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *Başlatıcı*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*: /\* işlev bildirimcisi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**   / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

Kapatma parantezinden hemen ardından noktalı virgül tarafından sonlandırılır ve bu nedenle hiçbir gövdeye sahip prototipe işlev tanımı aynı biçime sahip. Her iki durumda da dönüş türü bir işlev tanımında belirtilen dönüş türüne sahip kabul etmesi gerekir.

İşlev prototipleri, aşağıdaki önemli kullandığı vardır:

- Bunlar farklı dönüş türlerine işlevleri için dönüş türü kurmak **int**. İşlevler, döndürür ancak **int** değerleri prototipleri gerektirmez, prototipleri önerilir.

- Olmadan tam prototipleri, standart dönüştürmeler gerçekleştirilir, ancak türü veya sayıda bağımsız değişken parametre sayısı ile kontrol etmek için girişimde bulunulmaz.

- Prototipleri, bu işlev tanımlanmadan önce işlev işaretçileri başlatmak için kullanılır.

- Parametre listesinde işlev çağrısında bağımsız değişken işlev tanımında parametreler ile ilişkiyi denetlemek için kullanılır.

Dönüştürülen her parametrenin türü bağımsız değişkenler yığında işlev çağrısı yerleştirir yorumunu belirler. Bağımsız değişken ve parametre arasında tür uyuşmazlığı bağımsız değişkenler yığında yorumlanma neden olabilir. Örneğin, 16-bit bir bilgisayarda bir 16 bit işaretçi bağımsız değişken olarak geçirilir, ardından olarak bildirilen bir **uzun** parametresi, yığın üzerinde ilk 32 biti olarak yorumlanır bir **uzun** parametresi. Bu hata yalnızca ile ilgili sorunlar oluşturur **uzun** parametresi, ancak izleyen herhangi bir parametre. Tüm İşlevler için tam işlev prototipleri bildirerek bu tür hatalar da algılanabilir.

Böylece tanımına önünde (veya diğer kaynak dosyalarda) işlev için çağrılar için bağımsız değişken türü ve dönüş türü uyuşmazlığı denetlenebilir bir prototipi bir işlev özniteliklerini belirler. Örneğin, belirtirseniz **statik** depolama sınıfı tanımlayıcısı bir prototipteki da belirtmeniz gerekir **statik** işlev tanımında depolama sınıfı.

Parametre bildirimleri tamamlayın (`int a`) ile soyut Bildirimciler karma (`int`) aynı bildirimde. Örneğin, aşağıdaki bildirimi geçerlidir:

```C
int add( int a, int );
```

Prototip türünü hem bir tanımlayıcı için bir bağımsız değişken olarak geçirilen her bir ifade içerebilir. Ancak, bu tür tanımlayıcıları, yalnızca bildirimi sonuna kadar kapsama sahip. Prototip ayrıca değişkendir bağımsız değişken sayısı veya hiç bağımsız değişken geçirilir olgu yansıtabilir. Derleyici bunları ilgili tanılama iletileri üretilemiyor bu nedenle böyle bir liste uyuşmazlıkları, açığa değil. Bkz: [bağımsız değişkenleri](../c-language/arguments.md) tür denetimi hakkında daha fazla bilgi.

Microsoft C derleyicisi prototip kapsamında, artık ANSI uyumlu ile derleme yaparken **/Za** derleyici seçeneği. Bunun anlamı bildirirseniz bir **yapı** veya **birleşim** etiketi etiketi bir prototip içinde bu kapsamda yerine genel kapsamda girilir. Örneğin, ile derleme yaparken **/Za** ANSI uyumluluğu için hiçbir zaman bu işlev bir tür uyumsuzluğu hatası almadan çağırabilirsiniz:

```C
void func1( struct S * );
```

Kodunuzu düzeltmek için tanımlama veya bildirmek **yapı** veya **birleşim** işlev prototipi önce genel kapsamda:

```C
struct S;
void func1( struct S * );
```

Altında **/Ze**, etiket yine de genel kapsamda girilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
