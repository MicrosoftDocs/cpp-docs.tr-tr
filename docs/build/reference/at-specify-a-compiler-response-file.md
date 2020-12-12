---
description: 'Hakkında daha fazla bilgi edinin: @ (bir derleyici yanıt dosyası belirtme)'
title: '@ (Derleyici Yanıt Dosyasını Belirt)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: bd2859f7973723d93594693902e92ac3530d73ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182898"
---
# <a name="-specify-a-compiler-response-file"></a>@ (Derleyici Yanıt Dosyasını Belirt)

Bir derleyici yanıt dosyası belirtir.

## <a name="syntax"></a>Syntax

> **\@**<em>response_file</em>

## <a name="arguments"></a>Arguments

*response_file*<br/>
Derleyici komutlarını içeren bir metin dosyası.

## <a name="remarks"></a>Açıklamalar

Yanıt dosyası, komut satırında belirttiğiniz komutları içerebilir. Komut satırı bağımsız değişkenlerinizin 127 karakteri aşması durumunda bu yararlı olabilir.

**\@** Bir yanıt dosyası içinden seçeneği belirtmek mümkün değildir. Diğer bir deyişle, yanıt dosyası başka bir yanıt dosyası katıştıramaz.

Komut satırından istediğiniz kadar çok yanıt dosyası seçeneği belirtebilirsiniz (örneğin, `@respfile.1 @respfile.2` ).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

- Bir yanıt dosyası geliştirme ortamının içinden belirtilemiyor ve komut satırında belirtilmelidir.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneği program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
