---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: ab7682c8344d6fc36ded03e7ef885c83d2f19ab7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169051"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Windows Vista 'da ilk olarak bulunan Windows 'un adres alanı düzeni rastgele seçme (ASLR) özelliğini kullanarak yükleme zamanında rastgele bir şekilde yeniden temellenebilir bir yürütülebilir görüntü oluşturulup oluşturulmayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/DynamicBase**[ **: No**]

## <a name="remarks"></a>Açıklamalar

**/DynamicBase** seçeneği bir *yürütülebilir görüntünün*, bir. dll veya. exe dosyasının üst bilgisini değiştirerek uygulamanın yükleme zamanında rastgele bir şekilde yeniden yapılıp yapılmayacağını ve sanal adres ayırma rastgele olmasını, bu da Heap 'ler, yığınların ve diğer işletim sistemi ayırmalarının sanal bellek konumunu etkiler. **/DynamicBase** seçeneği, hem 32-bit hem de 64 bit görüntüler için geçerlidir. ASLR, Windows Vista ve sonraki işletim sistemlerinde desteklenir. Bu seçenek önceki işletim sistemleri tarafından yok sayılır.

Varsayılan olarak, **/DynamicBase** etkindir. Bu seçeneği devre dışı bırakmak için **/DynamicBase: No**kullanın. [/Highentropyva](highentropyva-support-64-bit-aslr.md) seçeneğinin bir etkisi olması için **/DynamicBase** seçeneği gereklidir.

## <a name="see-also"></a>Ayrıca bkz.

- [EDITBIN Seçenekleri](editbin-options.md)
- [Windows ISV yazılım güvenliği savunmaları](https://msdn.microsoft.com/library/bb430720.aspx)
