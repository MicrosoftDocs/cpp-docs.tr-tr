---
title: WSADATA yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WSADATA
dev_langs:
- C++
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75baf04ff1a380af8371f2d44a5295a3be65dc7e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446663"
---
# <a name="wsadata-structure"></a>WSADATA Yapısı

`WSADATA` Yapısı Windows Sockets başlatma bilgileri bir çağrı tarafından döndürülen depolamak için kullanılan `AfxSocketInit` genel işlev.

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

*wVersion*<br/>
Windows Yuvaları DLL kullanılacak çağıran bekliyor sürümü Windows yuva belirtimi.

*wHighVersion*<br/>
(Ayrıca yukarıdaki gibi kodlanmış) bu DLL destekleyen Windows yuva belirtimi en yüksek sürümü. Normalde, bu aynıdır *wVersion*.

*szDescription*<br/>
Satıcı Kimliği de dahil olmak üzere Windows Sockets uygulaması açıklamasını Windows Sockets DLL içine kopyalar null ile sonlandırılmış ASCII dize. Metin (en fazla 256 karakter uzunluğunda) tüm karakterleri içerebilir, ancak denetimi içeren ve karakter biçimlendirme karşı satıcıları dikkatli olmalıdır:, bu sokar bir uygulama için büyük olasılıkla (büyük olasılıkla kesilmiş) görüntülemek için bir durum iletisinde kullanılır.

*szSystemStatus*<br/>
Durum veya yapılandırma bilgileri Windows Sockets DLL içine kopyalar null ile sonlandırılmış ASCII dize. Bilgiler yalnızca veya kullanıcı için yararlı destek personeli Windows Sockets DLL Bu alan kullanmanız gerekir; bir uzantısı olarak değerlendirilmemelidir *szDescription* alan.

*iMaxSockets*<br/>
Tek bir işlem büyük olasılıkla açabilirsiniz yuva sayısı. Bir Windows Sockets uygulaması yuva oluşan küresel bir havuz ayırmak için herhangi bir işlem sağlayabilir. Alternatif olarak, bu işlem içi kaynak yuva için tahsis edebilirsiniz. Sayı da Windows Sockets DLL ya da ağ yazılımı yapılandırılan şekilde yansıtabilir. Uygulama yazarları, bu sayı, Windows Sockets uygulaması uygulama tarafından kullanılabilir olup kaba bir gösterge olarak kullanabilirsiniz. Örneğin, bir X Windows server denetleyebilir *iMaxSockets* ilk başlattığınızda: 8'den az ise, uygulama ağ yazılımı yeniden yapılandırmak için kullanıcı söyleyen bir hata iletisi görüntüler. (Bu bir durumda olduğundan *szSystemStatus* metin kullanılan.) Kuşkusuz belirli bir uygulamayı gerçekten tahsis edebileceğiniz bir garanti yoktur *iMaxSockets* diğer Windows Sockets uygulamaları kullanımda olabileceği yuva.

*iMaxUdpDg*<br/>
Bayt gönderilen ya da Windows Sockets uygulama tarafından alınan en büyük kullanıcı veri birimi Protokolü (UDP) veri biriminin boyutu. Uygulama, sınır uygular, *iMaxUdpDg* sıfırdır. Berkeley yuva birçok uygulamalarında (hangi gerekirse parçalanmış) UDP veri birimleri üzerinde 8192 bayt örtük bir sınırlama yoktur. Bir Windows Sockets uygulaması örneği için parçanın yeniden birleştirme arabellek tahsisine dayalı bir sınır uygulayabilir. En küçük değerini *iMaxUdpDg* için uyumlu bir Windows Sockets 512 uygulamasıdır. Değeri bağımsız olarak dikkat *iMaxUdpDg*, daha maksimum aktarım Birimi'nin (MTU) ağ için büyük bir yayın datagram göndermeye önerilmez. (Windows Sockets API'SİNİN MTU bulmak için bir mekanizma sağlamaz, ancak en az 512 bayt olması gerekir.)

*lpVendorInfo*<br/>
Uzak bir satıcıya özgü veri yapısı işaretçisi. Windows Yuvaları belirtimi kapsamı dışındadır (sağlandıysa) Bu yapı tanımıdır.

> [!NOTE]
>  MFC'de, `WSADATA` yapısı tarafından döndürülen `AfxSocketInit` , arama işlevi, `InitInstance` işlevi. Yapısı almak ve verilerden bilgi daha sonra kullanmanız gerekiyorsa, programınızda depolayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winsock2.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Afxsocketınit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

