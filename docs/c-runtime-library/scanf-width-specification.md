---
title: sacnf genişlik belirtimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- scanf
dev_langs:
- C++
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0052f4b270366b2f3aa1e1550f790efcb860597
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="scanf-width-specification"></a>sacnf Genişlik Belirtimi
Biçim dizeleri yorumu bu bilgileri uygulandığı `scanf` gibi güvenli sürümleri dahil olmak üzere işlevlerin ailesi `scanf_s`. Bu İşlevler normalde giriş akışı belirteçleri dizisi ayrılmıştır varsayalım. Belirteçleri boşluk (boşluk, sekme ya da yeni satır) tarafından veya bir sayısal veri türü sayısal metne dönüştürülemez ilk karakter belirtildiği gibi doğal sonuna sayısal türler söz konusu olduğunda ayrılır. Ancak, bir belirteç doğal bitişinden önce durdurmak için giriş ayrıştırma neden genişlik belirtimi kullanılabilir.  
  
 *Genişliği* karakter arasında oluşur belirtimi `%` ve adlı pozitif bir tamsayı içerebilir tür alan belirteci *genişliği* alan ve bir veya daha fazla karakter tür bir tamsayı türü olup olmadığına dair bir gösterge gibi alan değiştiricileri olarak düşünülebilecek alan boyutunu belirten **kısa** veya **uzun**. Bu tür karakterler boyutu önek olarak adlandırılır.  
  
## <a name="the-width-field"></a>Genişliği alanı  
 *Genişlik* Bu alan için okunacak en fazla karakter sayısını denetleme pozitif bir ondalık tamsayı bir alandır. En fazla *genişliği* karakterleri dönüştürülür ve karşılık gelen konumunda depolanan `argument`. Daha az *genişliği* karakter olabilir bir boşluk karakteri (boşluk, sekme ya da yeni satır) veya belirtilen biçimine göre dönüştürülemez karakter önce oluşursa okuma *genişliği* ulaşıldı.  
  
 Bu işlevler güvenli sürümleri tarafından gerekli arabellek boyutu bağımsız değişkeniyle kümesinden farklı ve ayrıdır genişlik belirtimi (yani, `scanf_s`, `wscanf_s`vb..). Aşağıdaki örnekte, genişlik belirtimi 20 olur kadar gösteren 20 giriş akışından okunamıyor karakterlerdir. Arabellek uzunluğu 21, olası 20 karakteri artı null Sonlandırıcı yer içeren değil:  
  
```  
char str[21];  
scanf_s("%20s", str, 21);  
```  
  
 Varsa *genişliği* alan kullanılmaz, `scanf_s` tüm belirteç dizeye okuma dener. Belirtilen boyut tüm belirteç tutmak için yeterince büyük değilse, hiçbir şey hedef dizeye yazılır. Varsa *genişliği* alanı belirtilmemişse, sonra ilk *genişliği* karakter belirteci null Sonlandırıcı hedef dizesiyle yazılır.  
  
## <a name="the-size-prefix"></a>Boyutu öneki  
 İsteğe bağlı önekleri **h**, **l**, **üm**, **I64**, ve **L** boyutunubelirtmek`argument`(uzun veya kısa, tek baytlı karakter ya da bunlar değiştiren türü karakter bağlı olarak, geniş karakter). Bu biçim belirtimi karakter türü karakter ile kullanılan `scanf` veya `wscanf` işlevleri aşağıdaki tabloda gösterildiği gibi değişkenleri yorumu belirtin. Türü önek **I64** bir Microsoft uzantısı ve ANSI uyumlu değil. "Karakter scanf işlevleri için tür" tablosunda karakterleri yazın ve anlamlarını açıklanan [scanf türü alan karakterleri](../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  **h**, **l**, ve **L** ön ekleri veri türü ile kullanıldığında Microsoft uzantıları `char`.  
  
### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>Scanf ve wscanf biçim türü tanımlayıcıları için boyutu önekleri  
  
|Belirtmek için|Ön ekini kullanın|Tür belirteci ile|  
|----------------|----------------|-------------------------|  
|**double**|**m**|**e**, **E**, **f**, **g**, veya **G**|  
|**uzun çift** (aynı çift)|**L**|**e**, **E**, **f**, **g**, veya **G**|  
|**uzun tamsayı**|**m**|**d**, **ı**, **o**, **x**, veya **X**|  
|**İmzasız Long int**|**m**|**u**|  
|**uzun uzun**|**üm**|**d**, **ı**, **o**, **x**, veya **X**|  
|`short int`|**h**|**d**, **ı**, **o**, **x**, veya **X**|  
|**İmzasız short int**|**h**|**u**|  
|__**Int64**|**I64**|**d**, **ı**, **o**, **u**, **x**, veya **X**|  
|Tek baytlı karakter ile `scanf`|**h**|**c** veya **C**|  
|Tek baytlı karakter ile `wscanf`|**h**|**c** veya **C**|  
|Uluslararası karakter ile `scanf`|**m**|**c** veya **C**|  
|Uluslararası karakter ile `wscanf`|**m**|**c**, veya **C**|  
|Tek baytlı - karakter dizesi `scanf`|**h**|**s** veya **S**|  
|Tek baytlı - karakter dizesi `wscanf`|**h**|**s** veya **S**|  
|Joker karakter dizesiyle `scanf`|**m**|**s** veya **S**|  
|Joker karakter dizesiyle `wscanf`|**m**|**s** veya **S**|  
  
 Aşağıdaki örneklerde **h** ve **l** ile `scanf_s` işlevleri ve `wscanf_s` işlevleri:  
  
```  
scanf_s("%ls", &x, 2);     // Read a wide-character string  
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character  
```  
  
 Güvenli olmayan bir işlev kullanıyorsanız `scanf` ailesi, önceki bağımsız değişkeni arabellek uzunluğu gösteren boyut parametresini atlayın.  
  
## <a name="reading-undelimited-strings"></a>Okuma sınırlandırılmamış dizeleri  
 Boşluk ile ayrılmış değil dizeleri okunacak karakter, köşeli karakter kümesi (**[]**) için yerine **s** (dize) türü karakteri. Köşeli ayraçlar karakter kümesinde bir denetim dize olarak adlandırılır. Karşılık gelen giriş alanını denetim dizesinde görünmez ilk karakterine okuyun. İlk karakter kümesi, bir düzeltme işareti olup olmadığını (**^**), etkisi tersine: karakter kümesini geri kalanı görünen ilk karakter için giriş alanını okuyun.  
  
 Unutmayın **% [a-z]** ve **% [z-a]** eşdeğer olarak yorumlanan **%[abcde...z]**. Bir ortak budur `scanf` işlevi uzantısı ancak ANSI standart gerekli olmadığı olduğunu unutmayın.  
  
## <a name="reading-unterminated-strings"></a>Okuma Sonlandırılmamış dize  
 Sonlandırma null karakteri ('\0') depolamadan bir dize depolamak için belirtimi kullanmak `%` *n *** c** nerede *n* ondalık bir tamsayıdır. Bu durumda, **c** türü karakteri bağımsız değişkeni bir karakter dizisi için bir işaretçi olduğunu gösterir. Sonraki *n* karakterleri giriş akışından okuma belirtilen konuma ve hiçbir null karakteri ('\0') eklenir. Varsa *n* belirtilmezse, varsayılan değer 1'dir.  
  
## <a name="when-scanf-stops-reading-a-field"></a>Scanf bir alanın okunması durduğunda  
 `scanf` İşlevi karakter her giriş alanını tarar. Çeşitli nedenlerle için bir boşluk karakteri erişmeden önce belirli bir giriş alanını okuma vermeyebilir:  
  
-   Belirtilen genişlik sınırına ulaştı.  
  
-   Sonraki karakteri dönüştürülemiyor belirtildiği gibi.  
  
-   Eşleştirilecek beklenen denetim dizesindeki bir karakter ile sonraki karakteri çakışıyor.  
  
-   Belirtilen karakter kümesinde görünmesi sonraki karakteri başarısız.  
  
 Herhangi bir nedenle zaman `scanf` işlevi durdurur giriş alanını okuma, sonraki giriş alanını ilk okunmamış karakterinde başlamak için değerlendirilir. Varsa, çakışan karakter kabul okunmamış ve sonraki giriş alanını ilk karakteri veya Giriş akışı sonraki okuma işlemlerinin ilk karakteri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)   
 [scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)