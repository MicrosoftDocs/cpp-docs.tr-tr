---
title: DEF dosyalarını kullanarak içeri aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1562e14b20e4e1dd96764414978889d6205179
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710547"
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

Bu durumda hesap için .def dosyasında SABİTİ görürse, geçerli Visual C++ bağlayıcı bir uyarı verir. Burada üstbilgi dosyasının değil listesinde bazı nesne dosyası derlemeniz olamaz, SABİTİ kullanmak için yalnızca gerçek neden olduğu **__declspec(dllimport)** prototipinde.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Uygulamaya Aktarma](../build/importing-into-an-application.md)
