---
title: /ZF (daha hızlı PDB oluşturma)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: bed37a189e3eb1eb7b55dbdee1f81f360eafa721
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315856"
---
# <a name="zf-faster-pdb-generation"></a>/ZF (daha hızlı PDB oluşturma)

RPC çağrıları mspdbsrv.exe en aza indirerek paralel yapılar, daha hızlı PDB oluşturmayı etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/ZF**

## <a name="remarks"></a>Açıklamalar

**/Zf** seçeneği kullanılırken daha hızlı oluşturulmasını PDB dosyaları için derleyici desteği sağlar [/MP (birden çok süreçle derleme)](mp-build-with-multiple-processes.md) seçeneği veya derleme sistemini (örneğin, [MSBuild ](/visualstudio/msbuild/msbuild-reference) veya [CMake](../cmake-projects-in-visual-studio.md)) birden çok cl.exe derleyicisi işlemler aynı anda çalışabilir. Bu seçenek derleyici ön ucu oluşturma türü dizinleri her türü kayıt PDB dosyası için derleme sonuna kadar gecikme neden olur ve ardından bunları her kayıt için bir RPC isteği yapan yerine mspdbsrv.exe, tek bir RPC çağrısı içindeki tüm istekleri. Birden çok cl.exe derleyicisi işlemler aynı anda çalıştırdığı bir ortamda mspdbsrv.exe işlemi RPC yükünü azaltarak bu üretilen derleme işi önemli ölçüde artırabilir.

Çünkü **/Zf** seçeneği yalnızca PDB oluşturma için geçerlidir, gerektirir [/zi](z7-zi-zi-debug-information-format.md) veya [/zi](z7-zi-zi-debug-information-format.md) seçeneği.

**/Zf** seçeneği olan Visual Studio 2017 sürüm 15.1, başında nerede, varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15.7 başlangıç Preview 3, bu seçenek varsayılan olarak açık olduğunda **/zi** veya **/zi** seçeneği etkinleştirilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zf** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik Listelenmiş Derleyici Seçenekleri](compiler-options-listed-alphabetically.md)<br/>
[/MP (Birden Çok Süreçle Derleme)](mp-build-with-multiple-processes.md)<br/>
