---
description: Daha fazla bilgi edinin:/ZF (daha hızlı PDB oluşturma)
title: /ZF (Daha hızlı PDB oluşturma)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: 6acf84de3c286131f470808505cdf0e895feeaeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178894"
---
# <a name="zf-faster-pdb-generation"></a>/ZF (Daha hızlı PDB oluşturma)

mspdbsrv.exe için RPC çağrılarını en aza indirerek paralel derlemelerde daha hızlı PDB oluşturmayı etkinleştirin.

## <a name="syntax"></a>Syntax

> **/ZF**

## <a name="remarks"></a>Açıklamalar

**/ZF** seçeneği, [/MP (birden çok işlem ile derleme)](mp-build-with-multiple-processes.md) seçeneği kullanılırken veya derleme sistemi (örneğin, [MSBuild](/visualstudio/msbuild/msbuild-reference) veya [cmake](../cmake-projects-in-visual-studio.md)) aynı anda birden çok cl.exe derleyici işlemini çalıştırabilmesine yönelik olarak pdb dosyalarının daha hızlı oluşturulması için derleyici desteği sağlar. Bu seçenek derleyicinin ön ucunun, derleme sonuna kadar PDB dosyasındaki her bir tür kaydı için tür dizinlerinin oluşturulmasını geciktirmesini ve sonra her kayıt için bir RPC isteği yapmak yerine mspdbsrv.exe tek bir RPC çağrısında tümünü ister. Bu, birden çok cl.exe derleyicisi işleminin aynı anda çalıştırıldığı bir ortamdaki mspdbsrv.exe işlemindeki RPC yükünü azaltarak derleme verimini önemli ölçüde iyileştirebilir.

**/ZF** SEÇENEĞI yalnızca pdb oluşturma için geçerli olduğundan, [/Zi](z7-zi-zi-debug-information-format.md) veya [/Zi](z7-zi-zi-debug-information-format.md) seçeneğini gerektirir.

**/ZF** seçeneği, Visual Studio 2017 sürüm 15,1 ' den başlayarak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,7 Preview 3 ' te başlayarak, bu seçenek varsayılan olarak **/Zi** veya **/Zi** seçeneği etkin olduğunda etkindir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/ZF** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik Listelenmiş Derleyici Seçenekleri](compiler-options-listed-alphabetically.md)<br/>
[/MP (birden çok Işlemle derleme)](mp-build-with-multiple-processes.md)<br/>
