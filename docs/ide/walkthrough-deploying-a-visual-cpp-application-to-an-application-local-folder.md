---
title: Bir Visual C++ uygulamasını yerel uygulama klasörüne dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04b97ebffe5e44c4743df3b67987f0d27bba8a8f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426282"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>İzlenecek Yol: Visual C++ Uygulamasını Yerel Uygulama Klasörüne Dağıtma

Visual C++ uygulaması dosyaları klasörüne kopyalayarak dağıtmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıkları yok. başka bir bilgisayar.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Bir yerel uygulama klasörüne bir uygulamayı dağıtmak için

1. İçindeki adımları izleyerek bir MFC uygulaması oluşturmayı ve [izlenecek yol: Kurulum projesi dağıtma bir Visual C++ Application By Using](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

1. MFC ve C çalışma zamanı (CRT) kitaplığı uygun dosyaları kopyalayın — Örneğin, bir x86 için platform ve Unicode desteği, kopya mfc100u.dll ve \Program Visual Studio 10.0\VC\redist\x86\—and gelen msvcr100.dll bunları \Release\ klasöründe bulunan yapıştırın MFC projenize. Kopyalamak için sahip olabileceğiniz diğer dosyalar hakkında daha fazla bilgi için bkz. [belirleme hangi DLL'lerin yeniden dağıtılacağını](../ide/determining-which-dlls-to-redistribute.md).

1. MFC uygulamasını Visual C++ kitaplıkları sahip ikinci bir bilgisayarda çalıştırın.

   1.  \Release\ klasörünün içeriğini kopyalayın ve ikinci bir bilgisayar üzerinde uygulama klasöründe yapıştırın.

   1.  Uygulamayı ikinci bir bilgisayarda çalıştırın.

   Visual C++ kitaplıkları uygulama yerel klasöründe kullanılabilir olmadığından uygulama başarıyla çalışır.

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım Örnekleri](../ide/deployment-examples.md)