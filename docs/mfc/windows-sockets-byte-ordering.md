---
title: "Windows Yuvaları: Bayt sıralama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5c4693951800056974fe51ad102e63f2662fa76e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-byte-ordering"></a>Windows Yuvaları: Bayt Sıralama
Bu makale ve iki yardımcı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makalede, bayt sıralama yer almaktadır. Diğer sorunlar makalelerinde ele alınmıştır: [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).  
  
 Kullanıyorsanız veya sınıfından türetilen [CAsyncSocket](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekir. Kullanıyorsanız veya sınıfından türetilen [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunları sizin için.  
  
## <a name="byte-ordering"></a>Bayt sıralama  
 Başka bir makine mimarileri bazen farklı bayt siparişler kullanarak verileri depolar. Örneğin, Intel tabanlı makineler Macintosh (Motorola) makineler ters sırada verileri depolar. "Little Endian," adlı Intel bayt sırası Ayrıca ağ standart "big Endian" sırasını tersidir. Aşağıdaki tabloda bu terimler açıklanmaktadır.  
  
### <a name="big--and-little-endian-byte-ordering"></a>Büyük ve küçük-Endian bayt sıralama  
  
|Bayt sıralama|Açıklama|  
|-------------------|-------------|  
|Big Endian|En önemli bir sözcük sol tarafta bayttır.|  
|Little Endian|En önemli bir sözcük sağ tarafta bayttır.|  
  
 Genellikle, ağ üzerinden gönderip veriler için bayt sırası dönüştürme hakkında endişelenmeniz gerekmez, ancak bazı durumlarda bayt siparişleri dönüştürmeniz gerekir.  
  
## <a name="when-you-must-convert-byte-orders"></a>Bayt siparişleri dönüştürürken gerekir  
 Aşağıdaki durumlarda bayt siparişleri dönüştürmeniz gerekir:  
  
-   Ağ, başka bir makineye göndermekte olduğunuz veri aksine tarafından yorumlanması için gereken bilgileri geçtiğiniz. Örneğin, geçebilir bağlantı noktaları ve ağ anlamalısınız adresleri.  
  
-   İle iletişim kuran sunucu uygulaması MFC uygulaması değildir (ve kaynak kodu için elinizde). İki makine bayt aynı sıralama paylaşmıyorsa bu bayt sırası dönüştürmelerde çağırır.  
  
## <a name="when-you-do-not-have-to-convert-byte-orders"></a>Ne zaman bayt siparişleri Dönüştür gerekmez  
 Aşağıdaki durumlarda bayt siparişleri dönüştürme işi kaçınabilirsiniz:  
  
-   Her iki ucuna makinelerde bayt değil değiştirilecek kabul edebilir ve her iki makine aynı bayt sırası kullanın.  
  
-   İle iletişim kuran bir MFC uygulaması sunucusudur.  
  
-   Açıkça, bayt siparişleri veya dönüştürmeniz gerekir olup olmadığını söyleyebilir şekilde sunucusu ile iletişim için kaynak koduna sahip.  
  
-   MFC sunucuya bağlantı noktası. Bunu yapmak oldukça kolaydır ve daha küçük, daha hızlı kod genellikle sonucu.  
  
 İle çalışma [CAsyncSocket](../mfc/reference/casyncsocket-class.md), kendiniz tüm gerekli bayt sırası dönüşümleri yönetmeniz gerekir. Windows Yuvaları "big Endian" bayt sırası modeli standartlaştıran ve bu sıra ve diğerlerinin arasında dönüştürme işlevleri sağlar. [CArchive](../mfc/reference/carchive-class.md), ancak ile kullandığınız [CSocket](../mfc/reference/csocket-class.md), ters ("little Endian") düzenini kullanır ancak `CArchive` , bayt sırası dönüştürmelerde ayrıntılarını ilgilenir. Bu standart uygulamalarınızda sıralama ya da Windows Sockets bayt sırası dönüştürme işlevleri kullanarak kullanarak, kodunuzu daha taşınabilir yapabilirsiniz.  
  
 Her iki ucuna iletişimin yazılırken MFC yuva kullanmak için ideal bir durumdur: her iki uçta MFC kullanma. MFC dışı uygulamalar, bir FTP sunucusu gibi büyük olasılıkla gerekir bayt-kendiniz arşiv nesnesine verileri geçirmeden önce değiştirme yönetmek iletişim kuracağı bir uygulama yazıyorsanız Windows Sockets dönüştürme yordamları kullanarak**ntohs**, **ntohl**, **htons**, ve **htonl**. MFC dışı uygulama ile iletişim kurulurken kullanılan bu işlevleri örneği, bu makalenin sonraki bölümlerinde görünür.  
  
> [!NOTE]
>  İletişimin diğer ucundaki MFC uygulaması olmadığında, ayrıca türetilmiş C++ nesneleri akış kaçınmalısınız `CObject` Arşiviniz içine alıcı bunları işleyebilen olmayacağı için. Bkz. Not [Windows Yuvaları: arşivlerle kullanılan yuvalara](../mfc/windows-sockets-using-sockets-with-archives.md).  
  
 Bayt siparişler hakkında daha fazla bilgi için Windows SDK'da bulunan Windows Sockets belirtime bakın.  
  
## <a name="a-byte-order-conversion-example"></a>Bayt sırası dönüştürme örneği  
 Seri hale getirme işlevi için aşağıdaki örnekte bir `CSocket` bir arşiv kullanan nesnesi. Bayt sırası dönüştürme işlevleri Windows Sockets API'SİNDE kullanma gösterilmektedir.  
  
 Bu örnek, hiçbir erişim kaynak koduna sahip bir MFC dışı sunucu uygulaması ile iletişim kuran istemci yazmakta olduğunuz bir senaryo gösterir. Bu senaryoda, MFC dışı sunucunun standart ağ bayt sırası kullandığını varsayın gerekir. Buna karşılık, MFC istemci uygulamanızın kullandığı bir `CArchive` nesnesi ile bir `CSocket` nesnesi ve `CArchive` "little Endian" bayt sırası, standart ağ karşıtı kullanır.  
  
 MFC dışı sunucusu ile iletişim kurmak planlama aşağıdakine benzer bir ileti paketi için kurulmuş bir protokol olduğunu varsayın:  
  
 [!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]  
  
 MFC açısından, bu şekilde ifade edilebilir:  
  
 [!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]  
  
 C++ ' ta bir `struct` temelde aynı sınıf olarak şeydir. `Message` Yapısında bulunabilir üye işlevleri gibi `Serialize` üye işlevi bildirimi yukarıda. `Serialize` Üye işlevi şuna benzeyebilir:  
  
 [!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]  
  
 Olduğundan Temizle uyuşmazlığı bayt bir uç MFC dışı sunucu uygulaması sıralamasını arasındaki bu örnek veri bayt sırası dönüştürmelerde çağırır ve `CArchive` MFC istemci uygulamanız diğer uçtaki kullanılır. Örnek Windows Sockets sağlayan bayt sırası dönüştürme işlevleri çeşitli gösterir. Aşağıdaki tabloda, bu işlevler açıklanmaktadır.  
  
### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows Yuvaları: bayt sırası dönüşüm işlevleri  
  
|İşlev|Amaç|  
|--------------|-------------|  
|**ntohs**|Bir 16 bit miktar konak bayt sırası (big Endian little Endian için) ağ bayt sırası Dönüştür.|  
|**ntohl**|32-bitlik bir miktar konak bayt sırası (big Endian little Endian için) ağ bayt sırası Dönüştür.|  
|**Htons**|Bir 16 bit miktar konak bayt sırası ağ bayt sırası (little Endian big Endian için) dönüştürün.|  
|**Htonl**|32-bitlik bir miktar konak bayt sırası ağ bayt sırası (little Endian big Endian için) dönüştürün.|  
  
 Başka bir Bu örnek diğer uçtaki iletişimin yuva uygulama MFC dışı uygulama olduğunda, aşağıdakine benzer yapmaktan kaçının gerekir noktasıdır:  
  
 `ar << pMsg;`  
  
 Burada `pMsg` gösteren bir işaretçidir sınıfından türetilen bir C++ nesnesine `CObject`. MFC uygulaması olsaydı olduğu gibi bu nesneler ve sunucu ile ilişkili ek MFC bilgileri, anlayabileceği değil gönderir.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: arka plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Yuvaları: Akış yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

