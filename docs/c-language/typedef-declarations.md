---
title: TypeDef bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7af5e89e66b179b4527fd35a042caf8ddb1c644
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100584"
---
# <a name="typedef-declarations"></a>Typedef Bildirimleri

Bir typedef bildiriminde bir typedef ile depolama sınıfı olarak bildirimidir. Yeni bir tür bildirimci olur. Typedef bildirimleri, zaten C tarafından tanımlanan türlerin veya, bildirilen türleri için daha kısa ya da daha anlamlı adları oluşturmak için kullanabilirsiniz. TypeDef adları değişebilir uygulama ayrıntılarını kapsüllemek olanak sağlar.

Bir typedef bildiriminde bir değişken olarak aynı şekilde yorumlanır veya işlev bildirimi ancak bildirim tarafından belirtilen tür varsayılarak yerine tanımlayıcı, türe ilişkin bir eşanlam haline gelir.

## <a name="syntax"></a>Sözdizimi

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları init-declarator-list*<sub>iyileştirilmiş</sub> **;**

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür tanımlayıcısı bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyici bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*depolama sınıfı tanımlayıcısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**tür tanımı**

*tür belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Geçersiz kılma**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısa**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uzun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kayan nokta**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**çift**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İmzalı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İşaretsiz**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya union tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit listesi belirticisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*TypeDef adı*

*TypeDef adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

Bir typedef bildiriminde türleri oluşturmaz unutmayın. Varolan türleri için eş anlamlı sözcükler ya da başka şekillerde belirtilebilir türleri için adlar oluşturur. Typedef adı bir tür tanımlayıcısı kullanıldığında, belirli tür tanımlayıcıları, ancak diğer ile birleştirilebilir. Kabul edilebilir değiştiriciler dahil **const** ve `volatile`.

TypeDef adları sıradan tanımlayıcıları ile ad alanı paylaşabilir (bkz [ad alanları](../c-language/name-spaces.md) daha fazla bilgi için). Bu nedenle, bir program typedef adı ve yerel kapsamı tanımlayıcısı tarafından aynı ada sahip olabilir. Örneğin:

```C
typedef char FlagType;

int main()
{
}

int myproc( int )
{
    int FlagType;
}
```

Bir yerel kapsamı tanımlayıcısı için bir typedef ile aynı adla bildirirken veya bir yapı veya birleşim iç kapsamda veya aynı kapsamda üyesi bildirdiğinizde, tür tanımlayıcısı belirtilmelidir. Bu örnekte, bu kısıtlama gösterilmektedir:

```C
typedef char FlagType;
const FlagType x;
```

Yeniden `FlagType` bir tanımlayıcı, bir yapı üyesinin veya birleşim üyesi, tür için ad sağlanmalıdır:

```C
const int FlagType;  /* Type specifier required */
```

Söyleyin için yeterli değil

```C
const FlagType;      /* Incomplete specification */
```

çünkü `FlagType` türü değil bildiriliyor tanımlayıcının bir parçası olarak alınır. Bu bildirim gibi bildirimi geçersiz olacak şekilde alınır

```C
int;  /* Illegal declaration */
```

Typedef, işaretçi, işlevi ve dizi türleri dahil olan her türlü bildirebilirsiniz. Yapı veya birleşim türü tanımlamadan önce bildirimiyle aynı görünürlük tanımını sahip olduğu sürece bir yapı veya birleşim türü işaretçisi için bir typedef adı bildirebilirsiniz.

TypeDef adları, kodun okunabilirliğini geliştirmek için kullanılabilir. Aşağıdaki bildirimleri üç `signal` ilk olmadan yapma tam olarak aynı türü belirtin herhangi bir typedef adları kullanın.

```C
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */

void ( *signal( int, void (*) (int)) ) ( int );
fv *signal( int, fv * );   /* Uses typedef type */
pfv signal( int, pfv );    /* Uses typedef type */
```

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler typedef bildirimleri gösterir:

```C
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */
```

Unutmayın `WHOLE` artık bir Değişken bildiriminde gibi kullanılabilir `WHOLE i;` veya `const WHOLE i;`. Ancak, bildirimi `long WHOLE i;` geçersiz olacaktır.

```C
typedef struct club
{
    char name[30];
    int size, year;
} GROUP;
```

Bu ifade `GROUP` olarak üç üyesi olan bir yapı türü. Bir yapı etiketi beri `club`, ayrıca belirtilirse, typedef adı (`GROUP`) veya yapı etiketi bildirimlerinde de kullanılabilir. Struct anahtar sözcüğü etiketiyle kullanmalıdır ve struct anahtar sözcüğü typedef adı ile kullanamazsınız.

```C
typedef GROUP *PG; /* Uses the previous typedef name
                      to declare a pointer            */
```

Türü `PG` işaretçisi olarak bildirilen `GROUP` sırayla bir yapı türü tanımlanmış bir tür.

```C
typedef void DRAWF( int, int );
```

Bu örnek türü sağlar `DRAWF` için hiçbir değer döndürerek ve iki tamsayı bağımsız değişken alan bir işlev. Bu, örneğin, anlamına bildirimi

```C
DRAWF box;
```

bildirime eşdeğerdir

```C
void box( int, int );
```

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)
