---
title: Typedef Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
ms.openlocfilehash: 3d477e33def7168d01f9c5f8a64579fed0b497eb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87190071"
---
# <a name="typedef-declarations"></a>Typedef Bildirimleri

Typedef bildirimi, depolama sınıfı olarak typedef içeren bir bildirimidir. Bildirimci yeni bir tür haline gelir. Zaten C veya bildirdiğiniz türler için tanımlanmış olan türler için daha kısa veya daha anlamlı adlar oluşturmak üzere typedef bildirimlerini kullanabilirsiniz. Typedef adları, değişebilir uygulama ayrıntılarını kapsüllemek için izin verir.

Bir typedef bildirimi, bir değişken veya işlev bildirimiyle aynı şekilde yorumlanır, ancak bildirim tarafından belirtilen türün olması yerine tanımlayıcı tür için bir eş anlamlı olur.

## <a name="syntax"></a>Sözdizimi

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-belirteçleri init-declarator-list*<sub>opt</sub> **;**

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı belirleyicisi bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi bildirimi-tanımlayıcılar*<sub>kabul</sub>

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`typedef`**

*tür belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`void`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`char`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`short`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`int`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`long`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`float`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`double`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`signed`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`unsigned`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union-Belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sabit Listesi belirticisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*TypeDef-adı*

*typedef-adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

Bir typedef bildiriminin tür oluşturmadığını unutmayın. Mevcut türler için eş anlamlıları veya diğer yollarla belirtilenebilir türlerin adlarını oluşturur. Bir typedef adı bir tür belirleyici olarak kullanıldığında, bazı tür belirticileriyle birleştirilebilir, ancak diğerleri değildir. Kabul edilebilir değiştiriciler **`const`** ve içerir **`volatile`** .

Typedef adları, ad alanını sıradan tanımlayıcılarla paylaşır (daha fazla bilgi için bkz. [ad alanları](../c-language/name-spaces.md) ). Bu nedenle, bir program bir typedef adına ve aynı ada sahip bir yerel kapsam tanımlayıcısına sahip olabilir. Örnek:

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

Bir typedef ile aynı ad ile bir yerel kapsam tanımlayıcısı bildirirken veya aynı kapsamda veya bir iç kapsamda bir yapının veya birleşimin üyesini bildirirken tür belirleyicisi belirtilmelidir. Bu örnekte bu kısıtlama gösterilmektedir:

```C
typedef char FlagType;
const FlagType x;
```

`FlagType`Bir tanımlayıcı, yapı üyesi veya birleşim üyesi için adı yeniden kullanmak için, tür sağlanmalıdır:

```C
const int FlagType;  /* Type specifier required */
```

Söylemek yeterli değildir

```C
const FlagType;      /* Incomplete specification */
```

Çünkü, `FlagType` yeniden bildirilebilecek bir tanımlayıcı değil türün bir parçası olmak için alınır. Bu bildirim, şunun gibi geçersiz bir bildirim olacak şekilde alınır

```C
int;  /* Illegal declaration */
```

İşaretçi, işlev ve dizi türleri dahil olmak üzere typedef ile herhangi bir tür bildirebilirsiniz. Tanımın bildirimle aynı görünürlüğe sahip olduğu sürece yapıyı veya birleşim türünü tanımladıktan önce bir yapı veya birleşim türü işaretçisi için bir typedef adı bildirebilirsiniz.

Typedef adları, kod okunabilirliğini geliştirmek için kullanılabilir. Aşağıdaki bildirimlerden üçü `signal` , ilki, herhangi bir typedef adının kullanılmadan önce tam olarak aynı türü belirtir.

```C
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */

void ( *signal( int, void (*) (int)) ) ( int );
fv *signal( int, fv * );   /* Uses typedef type */
pfv signal( int, pfv );    /* Uses typedef type */
```

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde typedef bildirimleri gösterilmektedir:

```C
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */
```

`WHOLE`Artık veya gibi bir değişken bildiriminde kullanılabileceğini unutmayın `WHOLE i;` `const WHOLE i;` . Ancak bildirim `long WHOLE i;` geçersiz olabilir.

```C
typedef struct club
{
    char name[30];
    int size, year;
} GROUP;
```

Bu ifade `GROUP` , üç üye içeren bir yapı türü olarak bildirir. Bir yapı etiketi `club` de belirtildiğinden, ya typedef Name ( `GROUP` ) ya da Structure etiketi bildirimlerinde kullanılabilir. Struct anahtar sözcüğünü etiketiyle birlikte kullanmanız gerekir ve struct anahtar sözcüğünü typedef adıyla birlikte kullanamazsınız.

```C
typedef GROUP *PG; /* Uses the previous typedef name
                      to declare a pointer            */
```

Türü, `PG` türü bir işaretçi olarak `GROUP` tanımlanır ve bu, sırasıyla bir yapı türü olarak tanımlanmıştır.

```C
typedef void DRAWF( int, int );
```

Bu örnek, `DRAWF` değer döndürülmeden ve iki int bağımsız değişken alan bir işlev için tür sağlar. Bu, örneğin, bildirimin

```C
DRAWF box;
```

Bildirime eşdeğerdir

```C
void box( int, int );
```

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
