---
title: '-Zc: auto (değişken türünü türet) | Microsoft Docs'
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
ms.openlocfilehash: b306a104b9f71d536684e62f6dda1cac45b1d9dd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612947"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (Değişken Türünü Türet)

**/Zc:auto [-]** derleyici seçeneği derleyiciye nasıl kullanılacağını [auto anahtar sözcüğü](../../cpp/auto-keyword.md) değişkenler bildirmek için. Varsayılan seçeneğini belirtirseniz **/Zc:auto**, derleyici, başlatma ifadesinden bildirilmiş bir değişken türü çıkarır. Belirtirseniz **/Zc:auto-**, derleyici değişkenin otomatik depolama sınıfı için ayırır.

## <a name="syntax"></a>Sözdizimi

> **/ZC:Auto**[**-**]  

## <a name="remarks"></a>Açıklamalar

C++ standardı bir özgün ve düzeltilmiş bir anlamı tanımlar `auto` anahtar sözcüğü. Visual C++ 2010'dan önce anahtar sözcüğü bir değişkende otomatik depolama sınıfı bildirir; diğer bir deyişle, bir değişken, yerel kullanım ömrüne sahiptir. Visual C++ 2010 ile başlayarak, anahtar sözcüğü bir değişken bildirimin başlatma ifadesinden türünü çıkarır. Kullanma **/Zc:auto [-]** derleyici seçeneği, derleyicinin özgün ve düzeltilmiş anlamını kullanmasını söylemeniz `auto` anahtar sözcüğü. **/Zc:auto** seçeneği varsayılan olarak açıktır. [/ Permissive-](permissive-standards-conformance.md) seçeneği, varsayılan ayarı değişmez **/Zc:auto**.

Derleyici, uygun bir tanılama iletisi sorunları kullanımınız `auto` anahtar sözcüğü geçerli çelişir **/Zc:auto** derleyici seçeneği. Daha fazla bilgi için [auto anahtar sözcüğü](../../cpp/auto-keyword.md). Visual C++ ile uyumluluk sorunları hakkında daha fazla bilgi için bkz. [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Bu derleyici seçeneğini Visual Studio'da ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/Zc:auto** veya **/Zc:auto-** için **ek seçenekler:** bölmesi.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
