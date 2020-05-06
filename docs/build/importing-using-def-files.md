---
title: DEF Dosyalarını Kullanarak İçeri Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
ms.openlocfilehash: 13a6a375d6200f73dd9845d057d1954c2b65485c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273423"
---
# <a name="importing-using-def-files"></a>DEF Dosyalarını Kullanarak İçeri Aktarma

**__Declspec (dllimport)** bir. def dosyası ile birlikte kullanmayı tercih ederseniz, yanlış kodlamanın soruna neden olma olasılığını azaltmak için. def dosyasını sabıt yerine verileri kullanacak şekilde değiştirmelisiniz:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

Aşağıdaki tabloda neden gösterilmektedir.

|Sözcükle|İçeri aktarma kitaplığı 'nda yayar|Aktarımları|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

**__Declspec (dllimport)** ve sabit kullanmak, açık bağlamaya `imp` izin vermek IÇIN oluşturulan. lib DLL içeri aktarma kitaplığındaki hem sürümü hem de oluşturulmamış adı listeler. **__Declspec (dllimport)** ve verilerin kullanılması yalnızca adının `imp` sürümünü listeler.

SABIT kullanırsanız, şu kod yapılarından herhangi biri erişmek `ulDataInDll`için kullanılabilir:

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\-veya

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

Ancak,. def dosyanızda VERI kullanıyorsanız, yalnızca şu tanıma derlenmiş kod değişkene `ulDataInDll`erişebilir:

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

Daha fazla risklidir çünkü ekstra yöneltme düzeyini kullanmayı unutursanız, değişkenin kendisi değil, içeri aktarma adres tablosunun işaretçisine erişebilirsiniz. Bu tür bir sorun, genellikle içeri aktarma adresi tablosu derleyici ve bağlayıcı tarafından salt okunurdur.

Geçerli MSVC bağlayıcı, bu durum için. def dosyasında sabıt değer görürse bir uyarı verir. SABIT kullanılması gereken tek gerçek neden, üstbilgi dosyasının prototip üzerinde **__declspec (dllimport)** listelamadığı bazı nesne dosyalarını yeniden derleyememenizdir.

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
