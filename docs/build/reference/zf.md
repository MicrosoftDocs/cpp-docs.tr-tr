---
title: "/ZF (daha hızlı PDB oluşturma) | Microsoft Docs"
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7012777643f993c552f79b58a02d4806c0ce4caa
ms.sourcegitcommit: c770a343def04ae77522708387c3f7c470e49969
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="zf-faster-pdb-generation"></a>/ZF (daha hızlı PDB oluşturma)

Daha hızlı PDB nesil paralel derlemelerde mspdbsrv.exe RPC çağrıları en aza indirerek etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/Zf**

## <a name="remarks"></a>Açıklamalar

**/Zf** seçeneğini kullanırken PDB dosyalarını daha hızlı oluşturulmasını için derleyici desteği etkinleştirir [/MP (birden çok süreçle derleme)](mp-build-with-multiple-processes.md) seçeneğini veya yapı sistem (örneğin, [MSBuild ](/visualstudio/msbuild/msbuild-reference) veya [CMake](../../ide/cmake-tools-for-visual-cpp.md)) birden çok cl.exe derleyici işlemler aynı anda çalışabilir. Bu seçenek türü dizinleri derleme sonuna kadar oluşturma PDB dosyasında her tür kaydı için gecikme derleyici ön uç neden olur ve ardından bunları her kayıt için bir RPC isteği yapan yerine mspdbsrv.exe, tek bir RPC çağrısı, tüm istekleri. Birden çok cl.exe derleyici işlemler aynı anda çalıştırdığı bir ortamda mspdbsrv.exe işlem RPC yükünü azaltarak bu yapı verimlilik önemli ölçüde artırabilir.

Çünkü **/Zf** seçeneği yalnızca PDB oluşturma için geçerlidir, gerektirir [/zı](z7-zi-zi-debug-information-format.md) veya [/zı](z7-zi-zi-debug-information-format.md) seçeneği.

**/Zf** seçeneği Visual Studio 2017 sürüm 15.1 başında olduğundan ve varsayılan olarak kapalıdır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zf** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik Listelenmiş Derleyici Seçenekleri](compiler-options-listed-alphabetically.md)  
[/MP (Birden Çok Süreçle Derleme)](mp-build-with-multiple-processes.md)  
