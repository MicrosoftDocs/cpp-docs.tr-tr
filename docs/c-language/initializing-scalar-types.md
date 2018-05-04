---
title: Skaler türleri başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef7356768a594694e0fcf3415c66ef63568a7cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="initializing-scalar-types"></a>Ölçekli Türleri Başlatma
Ne zaman başlatılırken skaler türleri, değeri *atama ifadesi* değişkene atanır. Atama dönüştürme kurallarını uygulayın. (Bkz [tür dönüşümleri](../c-language/type-conversions-c.md) dönüştürme kuralları hakkında bilgi için.)  
  
## <a name="syntax"></a>Sözdizimi  
 `declaration`:  
 *bildirim tanımlayıcıları init bildirimcisi listesi* kabul **;**  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci bildirim tanımlayıcıları* iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları* iptal et  
  
 *Init bildirimcisi listesi*:  
 *Init bildirimcisi*  
  
 *Init bildirimcisi listesi***,***init bildirimcisi*  
  
 *Init bildirimcisi*:  
 *bildirimcisi*  
  
 *bildirimcisi***=***Başlatıcı* / * skaler başlatma \*/  
  
 *Başlatıcı*:  
 *atama ifadesi*  
  
 Aşağıdaki kurallara uyarlar koşuluyla değişkenleri herhangi bir türde başlatabilirsiniz:  
  
-   Dosya kapsam düzeyinde bildirilen değişkenlerin başlatılabilir. Dış düzeyinde bir değişkeni açıkça başlatmazsanız, varsayılan olarak 0 olarak başlatılır.  
  
-   Sabit bir ifade ile bildirilen herhangi bir genel değişkeni başlatmak için kullanılan **statik** *depolama sınıfı tanımlayıcısı*. Değişkenleri bildirilen olmasını **statik** program yürütülmeye olduğunda başlatılır. Siz açıkça genel başlatmazsanız **statik** değişken 0 olarak varsayılan olarak başlatıldıktan ve işaretçi türü olan her üye bir null işaretçinin atanır.  
  
-   İle bildirilen değişkenlerin **otomatik** veya **kaydetmek** depolama sınıfı tanımlayıcısı yürütme denetimi geçirir bloğuna her zaman başlatılır, bunlar bildirilir içinde. Bir başlatıcı bildirimi üzerinden atlarsanız bir **otomatik** veya **kaydetmek** değişkeni, ilk değişkenin değeri olarak tanımlı değil. Otomatik ve kayıt değerlerini, başlatıcı bir sabit; olmaya sınırlı değil önceden tanımlanmış değerler, hatta işlev çağrıları içeren herhangi bir ifade olabilir.  
  
-   İlk değerleri için ve dış değişken bildirimleri için **statik** değişkenleri, harici veya dahili, olmalıdır sabit ifadeler. (Daha fazla bilgi için bkz: [sabit ifadeler](../c-language/c-constant-expressions.md).) Herhangi bir harici olarak bildirilen veya statik değişken adresini sabit olduğundan, bu bir dahili olarak bildirilen başlatmak için kullanılabilir **statik** işaretçi değişkeninin. Ancak, adresini bir **otomatik** değişken blok her yürütülmesi için farklı olabilir çünkü statik başlatıcı olarak kullanılamaz. Sabit veya değişken değerleri başlatmak için kullanabileceğiniz **otomatik** ve **kaydetmek** değişkenleri.  
  
-   Blok kapsamlı bir tanımlayıcı bildirimi varsa ve dış bağlantı tanımlayıcısı vardır, bildirimi bir başlatma sahip olamaz.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde başlatmaları gösterilmektedir:  
  
```  
int x = 10;   
```  
  
 Tamsayı değişken `x` sabit ifadesine başlatılmış `10`.  
  
```  
register int *px = 0;  
```  
  
 İşaretçinin `px` "null" işaretçi oluşturan 0 olarak başlatılır.  
  
```  
const int c = (3 * 1024);  
```  
  
 Bu örnek, sabit bir ifade kullanır `(3 * 1024)` başlatmak için `c` nedeniyle değiştirilemez bir sabit değere **const** anahtar sözcüğü.  
  
```  
int *b = &x;  
```  
  
 Bu bildirimi işaretçinin başlatır `b` başka bir değişkenin adresiyle `x`.  
  
```  
int *const a = &z;  
```  
  
 İşaretçinin `a` adlı bir değişkende adresi ile başlatılmış `z`. Ancak, beri bu belirtilen olacak şekilde bir **const**, değişkeni `a` yalnızca, hiçbir zaman değişiklik başlatılabilir. Her zaman aynı konuma işaret eder.  
  
```  
int GLOBAL ;  
  
int function( void )  
{  
    int LOCAL ;  
    static int *lp = &LOCAL;   /* Illegal initialization */  
    static int *gp = &GLOBAL;  /* Legal initialization   */  
    register int *rp = &LOCAL; /* Legal initialization   */  
}  
```  
  
 Genel değişkeni `GLOBAL` nedenle genel yaşam dış düzeyinde bildirilmiş. Yerel değişken `LOCAL` sahip **otomatik** depolama sınıfı ve yalnızca bu bildirilen işlevi yürütülmesi sırasında bir adresi vardır. Bu nedenle, başlatma girişiminde **statik** işaretçi değişkeninin `lp` adresiyle `LOCAL` izin verilmez. **Statik** işaretçi değişkeninin `gp` adresine başlatılabilir `GLOBAL` bu adrese her zaman aynı olduğundan. Benzer şekilde, `*rp` çünkü başlatılabilir `rp` yerel bir değişkendir ve nonconstant Başlatıcı olabilir. Blok girilir, her zaman `LOCAL` sonra atanan yeni bir adresi olan `rp`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlatma](../c-language/initialization.md)