---
title: '-Zc: auto (değişken türünü) | Microsoft Docs'
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:auto
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caa64f64b75145c850c6f6393570dc3f9ba0b0d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379581"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (Değişken Türünü Türet)

**/Zc:auto [-]** derleyici seçeneği derleyici nasıl kullanılacağını söyler [anahtar sözcüğü otomatik](../../cpp/auto-keyword.md) değişkenleri bildirmek için. Varsayılan seçenek belirtirseniz, **/Zc:auto**, derleyici, başlatma ifadesinden bildirilen değişkeninin türü deduces. Belirtirseniz **/Zc:auto-**, otomatik depolama sınıfı değişkenine derleyici ayırır.

## <a name="syntax"></a>Sözdizimi

> **/ZC:Auto**[**-**]  

## <a name="remarks"></a>Açıklamalar

C++ standart bir özgün ve için yeniden düzenlenen bir anlam tanımlar `auto` anahtar sözcüğü. Önce [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], anahtar sözcüğü otomatik depolama sınıfı bir değişkende bildirir; diğer bir deyişle, yerel bir yaşam süresi sahip bir değişken. İle başlayarak [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], anahtar sözcüğü bir değişken bildirimi 's başlatma ifadesinden türünü deduces. Kullanmak **/Zc:auto [-]** özgün ya da düzeltilmiş anlamını kullanmak için derleyicisi bildirmek için derleyici seçeneği `auto` anahtar sözcüğü. **/Zc:auto** seçeneği varsayılan olarak açıktır. [/ İzin veren-](permissive-standards-conformance.md) seçenek varsayılan ayar değiştirmez **/Zc:auto**.

Derleyici, uygun bir tanılama iletisi verir kullanımınız `auto` anahtar sözcüğü çelişir geçerli **/Zc:auto** derleyici seçeneği. Daha fazla bilgi için bkz: [anahtar sözcüğü otomatik](../../cpp/auto-keyword.md). Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/Zc:auto** veya **/Zc:auto-** için **ek seçenekler:** bölmesi.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
