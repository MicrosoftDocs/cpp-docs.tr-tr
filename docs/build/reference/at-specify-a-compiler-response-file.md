---
title: '@ (Derleyici Yanıt Dosyasını Belirt)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: 90dcadbb47cdc7eb4fa1ff039f5074a3141eac83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491318"
---
# <a name="-specify-a-compiler-response-file"></a>@ (Derleyici Yanıt Dosyasını Belirt)

Derleyici yanıt dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

> **\@**<em>response_file</em>

## <a name="arguments"></a>Arguments

*response_file*<br/>
Derleyici komutları içeren bir metin dosyası.

## <a name="remarks"></a>Açıklamalar

Bir yanıt dosyası, komut satırında belirtebilirdiniz herhangi bir komut içerebilir. Bu, komut satırı bağımsız değişkenleri 127 karakterden fazla faydalı olabilir.

Belirlemek mümkün değil **\@** içinde bir yanıt dosyası seçeneği öğesinden. Diğer bir deyişle, bir yanıt dosyası başka bir yanıt dosyası katıştırılamıyor.

Komut satırından kadar yanıt dosyası seçenekleri belirtebilirsiniz (örneğin, `@respfile.1 @respfile.2`) istediğiniz kadar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

- Bir yanıt dosyası gelen geliştirme ortamında belirtilemez ve komut satırında belirtilmelidir.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneğini program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
