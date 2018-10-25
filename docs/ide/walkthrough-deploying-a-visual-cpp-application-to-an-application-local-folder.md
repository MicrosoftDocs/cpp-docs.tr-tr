---
title: Bir Visual C++ uygulamasını yerel uygulama klasörüne dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
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
ms.openlocfilehash: 3db193c0537869e4b99bc4c0c94cc79c70f5e827
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060669"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>İzlenecek Yol: Visual C++ Uygulamasını Yerel Uygulama Klasörüne Dağıtma

Visual C++ uygulaması dosyaları klasörüne kopyalayarak dağıtmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıkları sahip olmayan başka bir bilgisayar.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Bir yerel uygulama klasörüne bir uygulamayı dağıtmak için

1. İçindeki adımları izleyerek bir MFC uygulaması oluşturmayı ve [izlenecek yol: Kurulum projesi dağıtma bir Visual C++ Application By Using](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

1. Visual Studio yükleme dizininde uygun MFC ve C çalışma zamanı (CRT) kitaplığı dosyaları kopyalama \\VC\\redist\\*sürüm* klasöründe ve ardından bunları \Release\ klasöründe bulunan yapıştırın MFC projenize. Kopyalamak için sahip olabileceğiniz diğer dosyalar hakkında daha fazla bilgi için bkz. [belirleme hangi DLL'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md).

1. MFC uygulamasını Visual C++ kitaplıkları sahip ikinci bir bilgisayarda çalıştırın.

   1. \Release\ klasörünün içeriğini kopyalayın ve ikinci bir bilgisayar üzerinde uygulama klasöründe yapıştırın.

   1. Uygulamayı ikinci bir bilgisayarda çalıştırın.

   Visual C++ kitaplıkları uygulama yerel klasöründe kullanılabilir olmadığından uygulama başarıyla çalışır.

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>
