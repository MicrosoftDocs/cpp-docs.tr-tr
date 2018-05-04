---
title: /ZF (daha hızlı PDB oluşturma) | Microsoft Docs
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
ms.openlocfilehash: 968ce17302fa608888c7ae2fedf695946b0119bd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zf-faster-pdb-generation"></a>/ZF (daha hızlı PDB oluşturma)

Daha hızlı PDB nesil paralel derlemelerde mspdbsrv.exe RPC çağrıları en aza indirerek etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/ZF**

## <a name="remarks"></a>Açıklamalar

**/Zf** seçeneğini kullanırken PDB dosyalarını daha hızlı oluşturulmasını için derleyici desteği etkinleştirir [/MP (birden çok süreçle derleme)](mp-build-with-multiple-processes.md) seçeneğini veya yapı sistem (örneğin, [MSBuild ](/visualstudio/msbuild/msbuild-reference) veya [CMake](../../ide/cmake-tools-for-visual-cpp.md)) birden çok cl.exe derleyici işlemler aynı anda çalışabilir. Bu seçenek türü dizinleri derleme sonuna kadar oluşturma PDB dosyasında her tür kaydı için gecikme derleyici ön uç neden olur ve ardından bunları her kayıt için bir RPC isteği yapan yerine mspdbsrv.exe, tek bir RPC çağrısı, tüm istekleri. Birden çok cl.exe derleyici işlemler aynı anda çalıştırdığı bir ortamda mspdbsrv.exe işlem RPC yükünü azaltarak bu yapı verimlilik önemli ölçüde artırabilir.

Çünkü **/Zf** seçeneği yalnızca PDB oluşturma için geçerlidir, gerektirir [/zı](z7-zi-zi-debug-information-format.md) veya [/zı](z7-zi-zi-debug-information-format.md) seçeneği.

**/Zf** seçeneği olan Visual Studio 2017 sürüm 15.1, başında Burada, varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15.7 başlangıç Preview 3, bu seçenek varsayılan olarak açık olduğunda **/zı** veya **/zi** seçeneği etkinleşir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zf** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik Listelenmiş Derleyici Seçenekleri](compiler-options-listed-alphabetically.md)<br/>
[/MP (Birden Çok Süreçle Derleme)](mp-build-with-multiple-processes.md)<br/>
