---
title: "AUTOCLIK ve AUTODRIV kullanarak uzak Otomasyonu çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: AUTOCLIK sample [MFC]
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b48e542743642b2cd765150ea523da2cfe93f6dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="running-remote-automation-using-autoclik-and-autodriv"></a>AUTOCLIK ve AUTODRIV Kullanarak Uzak Otomasyonu Çalıştırma
AUTOCLIK, uzak Otomasyonu hakkında daha fazla bilgi bir taban olarak kullanabileceğiniz basit bir Otomasyon sunucusu örnek uygulamasıdır. AUTODRIV AUTOCLIK yönlendiren basit bir otomasyon istemci uygulamasıdır. Uzak Otomasyon göstermek için bunları kullanabilirsiniz.  
  
#### <a name="to-install-autoclikexe-on-two-machines-and-drive-it-using-remote-automation"></a>AUTOCLIK yüklemek için. İki EXE'nin makineleri ve uzak Otomasyon kullanarak sürücü  
  
1.  Yükleme [AUTOCLIK](../visual-cpp-samples.md) örnek uygulama geliştirme makinenize.  
  
2.  AUTOCLIK oluşturun. EXE.  
  
3.  AUTOCLIK çalıştırın. Tek başına EXE deneyerek ve ardından kapatılmalıdır. Otomasyon sunucusu olarak bu kaydeder.  
  
4.  AUTOCLIK kopyalayın. Bir uzak makineye EXE var. çalıştırın ve ardından kapatılmalıdır.  
  
5.  AUTODRIV çalıştırın. EXE yerel makine ve çalışan AUTOCLIK başladığından emin olun. EXE. AUTODRIV hakkında daha fazla bilgi için. EXE, bkz: [AUTOCLIK](../visual-cpp-samples.md).  
  
6.  Uzak makinede AUTMGR32 başlatın. EXE (Otomasyon Yöneticisi).  
  
7.  Uzak makinede RACMGR32 başlatın. EXE (Uzak Otomasyon Bağlantı Yöneticisi).  
  
8.  Uzak Otomasyon Bağlantı Yöneticisi gelen AutoClik.Document seçin **OLE sınıfları** listesi.  
  
9. Bir sistem güvenlik ilkesinden seçin **istemci erişimi** sekmesini AutoClik.Document için istemci erişim vermek için.  
  
10. Yerel makinede RACMGR32 başlatın. EXE ve gelen select AutoClik.Document **OLE sınıfları** listesi.  
  
11. Gelen **sunucu bağlantısı** sekmesinde, her iki ağ adresi uzak makineye ve uygun ağ protokolü seçin.  
  
12. Seçili AutoClik.Document hala ile **OLE sınıfları** liste kutusunda, seçin **uzak** komutunu `Register` menüsü.  
  
13. Yerel makinede AUTODRIV çalıştırın. EXE veya eşdeğer AUTOCLIK. Bir MFC yerine bir Visual Basic sahip olmak istiyorsanız MAK Visual Basic projesinde istemci.  
  
 Uzak makinede şimdi yerel istemci tarafından başlatılan komutlar yürütülürken AUTOCLIK görüyor olmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzak Otomasyon](../mfc/remote-automation.md)

