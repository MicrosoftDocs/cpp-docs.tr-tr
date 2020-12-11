---
description: 'Hakkında daha fazla bilgi edinin: DEF dosyalarını kullanarak Içeri aktarma'
title: DEF Dosyalarını Kullanarak İçeri Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
ms.openlocfilehash: 9eb4face47bf999daa8f969282cc621708a76006
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156157"
---
# <a name="importing-using-def-files"></a>DEF Dosyalarını Kullanarak İçeri Aktarma

**`__declspec(dllimport)`** Bir. def dosyası ile birlikte kullanmayı seçerseniz, yanlış kodlamanın soruna neden olmasının olasılığını azaltmak için. def dosyasını sabit yerıne verileri kullanacak şekilde değiştirmelisiniz:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

Aşağıdaki tabloda neden gösterilmektedir.

|Sözcükle|İçeri aktarma kitaplığı 'nda yayar|Dışarı Aktarmalar|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

**`__declspec(dllimport)`** Ve sabit kullanmak, `imp` Açık bağlamaya izin vermek için oluşturulan. lib DLL içeri aktarma kitaplığındaki hem sürümü hem de oluşturulmamış adı listeler. **`__declspec(dllimport)`** Ve veri kullanımı, yalnızca `imp` adının sürümünü listeler.

SABIT kullanırsanız, şu kod yapılarından herhangi biri erişmek için kullanılabilir `ulDataInDll` :

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\-veya

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

Ancak,. def dosyanızda VERI kullanıyorsanız, yalnızca şu tanıma derlenmiş kod değişkene erişebilir `ulDataInDll` :

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

Daha fazla risklidir çünkü ekstra yöneltme düzeyini kullanmayı unutursanız, değişkenin kendisi değil, içeri aktarma adres tablosunun işaretçisine erişebilirsiniz. Bu tür bir sorun, genellikle içeri aktarma adresi tablosu derleyici ve bağlayıcı tarafından salt okunurdur.

Geçerli MSVC bağlayıcı, bu durum için. def dosyasında sabıt değer görürse bir uyarı verir. SABIT kullanılması gereken tek gerçek neden, üstbilgi dosyasının prototip üzerinde listelamadığı bazı nesne dosyalarını yeniden derleyememenizdir **`__declspec(dllimport)`** .

## <a name="see-also"></a>Ayrıca bkz.

[Bir uygulamaya aktarma](importing-into-an-application.md)
