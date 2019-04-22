---
title: Bir Visual C++ uygulamasını yerel uygulama klasörüne dağıtma
ms.date: 09/17/2018
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
ms.openlocfilehash: 33edf4bb736fad62928e11dd0550af6640d411ac
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787068"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>İzlenecek yol: Bir Visual C++ uygulamasını yerel uygulama klasörüne dağıtma

Visual C++ uygulaması dosyaları klasörüne kopyalayarak dağıtmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıkları sahip olmayan başka bir bilgisayar.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Bir yerel uygulama klasörüne bir uygulamayı dağıtmak için

1. İçindeki adımları izleyerek bir MFC uygulaması oluşturmayı ve [izlenecek yol: Bir kurulum projesi kullanarak Visual C++ uygulamasını dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

1. Visual Studio yükleme dizininde uygun MFC ve C çalışma zamanı (CRT) kitaplığı dosyaları kopyalama \\VC\\redist\\*sürüm* klasöründe ve ardından bunları \Release\ klasöründe bulunan yapıştırın MFC projenize. Kopyalamak için sahip olabileceğiniz diğer dosyalar hakkında daha fazla bilgi için bkz. [belirleme hangi DLL'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md).

1. MFC uygulamasını Visual C++ kitaplıkları sahip ikinci bir bilgisayarda çalıştırın.

   1. \Release\ klasörünün içeriğini kopyalayın ve ikinci bir bilgisayar üzerinde uygulama klasöründe yapıştırın.

   1. Uygulamayı ikinci bir bilgisayarda çalıştırın.

   Visual C++ kitaplıkları uygulama yerel klasöründe kullanılabilir olmadığından uygulama başarıyla çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>
