---
description: 'Hakkında daha fazla bilgi edinin: Izlenecek yol: uygulama yerel klasörüne Visual C++ uygulama dağıtma'
title: Uygulama yerel klasörüne Visual C++ uygulama dağıtma
ms.date: 04/23/2019
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
ms.openlocfilehash: c06015ea32bb9f54653e350966bd8089c98628b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135947"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>İzlenecek Yol: Visual C++ Uygulamasını Yerel Uygulama Klasörüne Dağıtma

Dosyaları klasörüne kopyalayarak bir Visual C++ uygulamasının nasıl dağıtılacağını açıklar.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıklarına sahip olmayan başka bir bilgisayar.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Uygulamayı yerel bir klasöre dağıtmak için

1. [Izlenecek yol: bir kurulum projesi kullanarak Visual C++ uygulaması dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)bölümündeki ADıMLARı izleyerek MFC uygulaması oluşturun ve oluşturun.

1. Uygun MFC ve C Run-Time (CRT) kitaplık dosyalarını VC Redist sürüm klasöründeki Visual Studio yükleme dizininden kopyalayın \\ \\ \\  ve ardından bunları MFC projenizin \Release\ klasörüne yapıştırın. Kopyalamanız gerekebilecek diğer dosyalar hakkında daha fazla bilgi için bkz. [hangi dll 'lerin yeniden dağıtılacağını belirleme](determining-which-dlls-to-redistribute.md).

1. MFC uygulamasını Visual C++ kitaplıkları olmayan ikinci bir bilgisayarda çalıştırın.

   1. \Release\ klasörünün içeriğini kopyalayın ve ikinci bilgisayardaki uygulama klasörüne yapıştırın.

   1. Uygulamayı ikinci bilgisayarda çalıştırın.

   Visual C++ kitaplıkları, uygulama yerel klasöründe kullanılabilir olduğundan uygulama başarıyla çalışıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım örnekleri](deployment-examples.md)<br/>
