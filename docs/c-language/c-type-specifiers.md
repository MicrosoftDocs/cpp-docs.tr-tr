---
title: C Tür Tanımlayıcıları
ms.date: 01/29/2018
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
ms.openlocfilehash: 1191cf4d2912cda535547f465fe4bfbedebe8fa2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313200"
---
# <a name="c-type-specifiers"></a>C Tür Tanımlayıcıları

Bildirimlerinde tür belirticileri bir değişken veya işlev bildiriminin türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

*tür belirleyicisi* &nbsp; &nbsp; &nbsp;: &nbsp; **void** &nbsp; **double** **char** &nbsp; **short** &nbsp; **int** &nbsp; **long** **float** **unsigned** **signed** *enum-specifier* *typedef-name* *struct-or-union-specifier* char short int Long float çift &nbsp;imzalı işaretsiz struct-or-Union-belirleyicisi &nbsp;enum-belirleyicisi &nbsp;typedef-Name &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;

**İmzalı karakter**, **işaretli Int**, **imzalanmış kısa tamsayı**ve **imzalı long int** türleri, **imzasız** karşılıklarıyla ve **numaralandırıcılarıyla**birlikte *tamsayı* türleri olarak adlandırılır. **Float**, **Double**ve **Long Double** tür belirticileri *kayan* veya *kayan nokta* türleri olarak adlandırılır. Bir değişken veya işlev bildiriminde, herhangi bir integral veya kayan nokta tür belirleyicisi kullanabilirsiniz. Bir bildirimde bir *tür belirleyicisi* sağlanmazsa, **int**olarak alınır.

**İmzalanmış** ve **işaretsiz** olan isteğe bağlı anahtar sözcükler, **enum**dışında herhangi bir integral türünden önce veya sonra da kullanılabilir ve yalnızca tür belirticileri olarak de kullanılabilir ve bu durumda, sırasıyla **imzalı int** ve **işaretsiz int**olarak anlaşılabilirler. Tek başına kullanıldığında, **int** anahtar sözcüğünün **imzalanacağı**varsayılır. Tek başına kullanıldığında, **Long** ve **Short** anahtar sözcükleri **long int** ve **short int**olarak anlaşılmıştır.

Sabit listesi türleri temel türler olarak değerlendirilir. Numaralandırma türleri için tür belirticileri, [numaralandırma bildirimlerinde](../c-language/c-enumeration-declarations.md)ele alınmıştır.

**Void** anahtar sözcüğünün üç kullanımı vardır: bir işlev dönüş türü belirtmek için, bağımsız değişken içermeyen bir işlev için bağımsız değişken türü listesi belirtmek ve belirtilmemiş bir tür işaretçisi belirtmek için. **Void** türünü, hiçbir değer döndürmeyen veya belirtilmemiş bir türe işaretçi bildiren işlevleri bildirmek için kullanabilirsiniz. Bir işlev adından sonra parantez içinde tek başına göründüğünde **void** hakkında bilgi için bkz. [bağımsız değişkenler](../c-language/arguments.md) .

**Microsoft'a Özgü**

Tür denetimi artık ANSI uyumludur; Bu, Type **Short** ve Type **int** farklı türlerdir. Örneğin, bu, derleyicinin önceki sürümleri tarafından kabul edilen Microsoft C derleyicisinde yeniden tanımlama.

```C
int   myfunc();
short myfunc();
```

Bu sonraki örnek ayrıca farklı türlere yöneltme hakkında bir uyarı oluşturur:

```C
int *pi;
short *ps;

ps = pi;  /* Now generates warning */
```

Microsoft C derleyicisi Ayrıca, oturum açma farkları için uyarılar üretir. Örneğin:

```C
signed int *pi;
unsigned int *pu

pi = pu;  /* Now generates warning */
```

Tür **void** ifadeler yan etkiler için değerlendirilir. Herhangi bir şekilde **void** türü olan bir ifadenin (varolmayan) değerini kullanamaz veya void bir ifadeyi (örtük veya açık dönüştürmeye göre) **void**dışında **herhangi bir türe** dönüştürebilirsiniz. **Void** ifadesinin gerekli olduğu bir bağlamda başka herhangi bir türün ifadesini kullanırsanız, değeri atılır.

ANSI belirtimine uymak için, <strong>void\* </strong> <strong>int\*</strong>olarak kullanılamaz. Belirtilmemiş bir türün işaretçisi olarak yalnızca **void** <strong>\*</strong> kullanılabilir.

**SON Microsoft 'a özgü**

[Typedef bildirimleri bölümünde açıklandığı](../c-language/typedef-declarations.md)gibi, **typedef** bildirimleriyle ek tür belirticileri oluşturabilirsiniz. Her türün boyutu hakkında bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
