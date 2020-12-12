---
description: 'Hakkında daha fazla bilgi edinin: `auto` Storage-Class Belirleyicisi'
title: auto Depolama Sınıfı Tanımlayıcısı
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: a20e599ca7189548f92a78ff378e3b5f9f202b3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279876"
---
# <a name="auto-storage-class-specifier"></a>`auto` Storage-Class Belirleyicisi

**`auto`** Depolama sınıfı tanımlayıcısı, yerel yaşam süresine sahip bir değişken, bir otomatik değişken bildirir. Bir **`auto`** değişken yalnızca bildirildiği blokta görünür. Değişkenlerin bildirimleri **`auto`** , [başlatma](../c-language/initialization.md)bölümünde anlatıldığı gibi başlatıcıları içerebilir. **`auto`** Depolama sınıfına sahip değişkenler otomatik olarak başlatılmadığından, bunları bildirdiğinizde açıkça başlatmalısınız ya da bunları blok içindeki deyimlerde ilk değerlerini atamanız gerekir. Başlatılmamış **`auto`** değişkenlerin değerleri tanımsız. ( **`auto`** **`register`** Bir başlatıcı verilirse yerel değişken veya depolama sınıfı her seferinde başlatıldığında başlatılır.)

Bir iç **`static`** değişken (yerel veya blok kapsamına sahip bir statik değişken), bir öğenin adresi sabit olmadığından herhangi bir dış öğe veya öğe adresiyle başlatılabilir **`static`** , ancak başka bir öğenin adresiyle başlatılabilir **`auto`** **`auto`** .

## <a name="see-also"></a>Ayrıca bkz.

[`auto` Sözcükle](../cpp/auto-cpp.md)
