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

Kullanmayı tercih ederseniz **__declspec(dllimport)** .def dosyası ile birlikte kodlama yanlış bir soruna neden olasılığını azaltmak için veri SABİTİ yerine kullanılacak .def dosyasını değiştirmeniz gerekir:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

Aşağıdaki tabloda neden olduğunu göstermektedir.

|Anahtar sözcüğü|İçeri aktarma kitaplığı'nda yayar|Dışarı aktarma|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

Kullanarak **__declspec(dllimport)** ve sabit listelerini her ikisi de `imp` sürümü ve DLL .lib düzenlenmemiş adını açık bağlama izin verecek şekilde oluşturulan kitaplık içeri aktarın. Kullanarak **__declspec(dllimport)** ve veri listeleri yalnızca `imp` adının sürümü.

SABİTİ kullanıyorsanız, aşağıdaki kod yapılarından birini kullanılabilir erişimi `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\-veya -

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

Ancak, .def dosyasında veri kullanırsanız, yalnızca aşağıdaki tanımıyla derlenmiş kod değişkenine erişebileceği `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

SABİTİ kullanarak olduğundan daha sakıncalıdır ek yöneltme düzeyi kullanılacak unutursanız, potansiyel olarak içeri aktarma adres tablosunun işaretçi değişkenine erişebilir — değişkenin kendisine değil. İçeri aktarma adres tablosunda derleyici ve bağlayıcı tarafından salt okunur yapıldığı için bu tür sorunlar genellikle bir erişim ihlali olarak bildirilebilir.

Bu durumda hesap için .def dosyasında SABİTİ görürse geçerli MSVC bağlayıcı bir uyarı verir. Burada üstbilgi dosyasının değil listesinde bazı nesne dosyası derlemeniz olamaz, SABİTİ kullanmak için yalnızca gerçek neden olduğu **__declspec(dllimport)** prototipinde.

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
