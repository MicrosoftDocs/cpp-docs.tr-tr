---
title: auto Depolama Sınıfı Tanımlayıcısı
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: 6bd36fd534602a5a4df95047a830058e8c5ef163
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313473"
---
# <a name="auto-storage-class-specifier"></a>auto Depolama Sınıfı Tanımlayıcısı

**Auto** depolama sınıfı tanımlayıcısı, yerel yaşam süresine sahip bir değişken otomatik değişken bildirir. **Otomatik** değişken yalnızca bildirildiği blokta görünür. **Otomatik** değişkenlerin bildirimleri, [başlatma](../c-language/initialization.md)bölümünde anlatıldığı gibi başlatıcıları içerebilir. **Otomatik** depolama sınıfına sahip değişkenler otomatik olarak başlatılmadığından, bunları bildirdiğinizde açıkça başlatmalısınız ya da bunları blok içindeki deyimlerde ilk değerlerini atamanız gerekir. Başlatılmamış **Otomatik** değişkenlerin değerleri tanımsız. (Bir başlatıcı verilirse **Otomatik** veya **yazmaç** depolama sınıfının yerel bir değişkeni her seferinde başlatıldığında başlatılır.)

Bir iç **statik** değişken (yerel veya blok kapsamına sahip bir statik değişken), bir **Otomatik** öğenin adresi sabit olmadığından herhangi bir dış veya **statik** öğe adresiyle başlatılabilir, ancak başka bir **Otomatik** öğenin adresi ile kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../cpp/auto-keyword.md)
