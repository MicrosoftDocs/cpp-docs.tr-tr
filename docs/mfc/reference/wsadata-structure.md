---
title: "WSADATA yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WSADATA
dev_langs:
- C++
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24cfbeb0e917914881587cb70fd345a903a08ecc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wsadata-structure"></a>WSADATA Yapısı
`WSADATA` Yapısı için bir çağrı tarafından döndürülen Windows Sockets başlatma bilgileri depolamak için kullanılan `AfxSocketInit` genel işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct WSAData {  
    WORD wVersion;  
    WORD wHighVersion;  
    char szDescription[WSADESCRIPTION_LEN+1];  
    char szSystemStatus[WSASYSSTATUS_LEN+1];  
    unsigned short iMaxSockets;  
    unsigned short iMaxUdpDg;  
    char FAR* lpVendorInfo;  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 *wVersion*  
 Windows Yuvaları DLL kullanmak için arayan beklediğini sürümü Windows Sockets belirtimi.  
  
 *wHighVersion*  
 (Ayrıca olarak yukarıdaki kodlanmış) bu DLL destekleyen Windows Sockets belirtimi en yüksek sürümü. Normalde, bu aynıdır **wVersion**.  
  
 *szDescription*  
 Satıcı Kimliği de dahil olmak üzere Windows Sockets uygulaması açıklamasını içine Windows Sockets DLL kopyalar null ile sonlandırılmış ASCII dize. Metin (uzunluğu en fazla 256 karakter) herhangi bir karakter içerebilir, ancak karakter biçimlendirme ve denetim dahil karşı satıcılar dikkatli olmalıdır: bir durum iletisinde (büyük olasılıkla kesilmiş) görüntülemek için bu sokar bir uygulama için en olası kullanımı içindir.  
  
 *szSystemStatus*  
 İçine ilgili durum ya da yapılandırma bilgileri Windows Sockets DLL kopyalar null ile sonlandırılmış ASCII dize. Bilgiler yalnızca veya kullanıcı için yararlı personele destek Windows Sockets DLL Bu alan kullanmalısınız; Uzantı düşünülmemelidir **szDescription** alan.  
  
 *iMaxSockets*  
 Tek bir işlem olası açabilirsiniz yuva sayısı. Bir Windows Sockets uygulamasını herhangi bir işlem için ayırma için genel bir yuva havuzu sağlayabilirsiniz; Alternatif olarak, bu yuva için işlem başına kaynakları ayırabilirsiniz. Sayı Windows Sockets DLL ya da ağ yazılımı yapılandırılan yolu da yansıtabilirsiniz. Uygulama yazarları bu numara, Windows Sockets uygulaması uygulama tarafından kullanılabilir olup kaba bir gösterge olarak kullanabilirsiniz. Örneğin, bir X Windows server kontrol **iMaxSockets** ilk kez başlatıldığında: 8'den az ise, uygulama ağ yazılımı yeniden yapılandırmak için kullanıcı söyleyen bir hata iletisi görüntüler. (Bu bir durumdur, **szSystemStatus** metin kullanılan.) Belli ki belirli bir uygulamayı gerçekten ayırabileceğiniz garantisi yoktur **iMaxSockets** yuva bu yana diğer Windows Sockets uygulamaları kullanımda olabilir.  
  
 *iMaxUdpDg*  
 Gönderilen veya Windows Sockets uygulaması tarafından alınan en büyük kullanıcı veri birimi Protokolü (UDP) datagram bayt cinsinden boyutu. Uygulama, sınır uygular, **iMaxUdpDg** sıfırdır. Berkeley yuva birçok uygulamalarında (hangi gerekirse parçalanmış) UDP veri birimleri üzerinde 8192 bayt örtük bir sınırı yoktur. Windows Yuvaları uygulama örneği için parça yeniden birleştirme arabellek tahsisine dayalı bir sınır uygulayabilir. En küçük değerini **iMaxUdpDg** için uyumlu bir Windows Sockets 512 uygulamasıdır. Değeri bağımsız olarak unutmayın **iMaxUdpDg**, daha maksimum aktarım Birimi'nin (MTU) ağ için büyük yayın bir veri birimi göndermeye önerilmez. (Windows Sockets API MTU bulmak için bir mekanizma sağlamaz, ancak en az 512 bayt olmalıdır.)  
  
 *lpVendorInfo*  
 Bir satıcıya özgü veri yapısı için uzak bir işaretçi. Windows Yuvaları belirtimi kapsamı dışındadır (sağlandıysa) Bu yapı tanımıdır.  
  
> [!NOTE]
>  MFC'de, `WSADATA` yapısı tarafından döndürülen `AfxSocketInit` , arama işlevi, `InitInstance` işlevi. Yapısı almak ve bilgi daha sonra kullanmanız gerekiyorsa, programınıza saklayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winsock2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

