---
title: "Düğme stilleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BS_DEFPUSHBUTTON
- BS_NOTIFY
- BS_MULTILINE
- BS_AUTOCHECKBOX
- BS_3STATE
- BS_BITMAP
- BS_TOP
- BS_PUSHBUTTON
- BS_PUSHLIKE
- BS_AUTO3STATE
- BS_CHECKBOX
- BS_AUTORADIOBUTTON
- BS_RADIOBUTTON
- BS_OWNERDRAW
- BS_LEFT
- BS_USERBUTTON
- BS_RIGHTBUTTON
- BS_RIGHT
- BS_LEFTTEXT
- BS_TEXT
- BS_BOTTOM
- BS_GROUPBOX
- BS_FLAT
- BS_VCENTER
- BS_ICON
- BS_CENTER
dev_langs: C++
helpviewer_keywords:
- BS_NOTIFY constant [MFC]
- BS_RIGHTBUTTON constant [MFC]
- styles [MFC], button objects
- BS_USERBUTTON constant [MFC]
- BS_VCENTER constant [MFC]
- BS_PUSHLIKE constant [MFC]
- BS_RADIOBUTTON constant [MFC]
- BS_PUSHBUTTON constant [MFC]
- BS_DEFPUSHBUTTON constant [MFC]
- BS_LEFTTEXT constant [MFC]
- button objects (CButton), button styles
- BS_AUTO3STATE constant [MFC]
- BS_3STATE constant [MFC]
- BS_OWNERDRAW constant [MFC]
- BS_AUTORADIOBUTTON constant [MFC]
- BS_GROUPBOX constant [MFC]
- BS_BITMAP constant [MFC]
- BS_CENTER constant [MFC]
- BS_MULTILINE constant [MFC]
- BS_BOTTOM constant [MFC]
- BS_FLAT constant [MFC]
- BS_AUTOCHECKBOX constant [MFC]
- BS_RIGHT constant [MFC]
- BS_CHECKBOX constant [MFC]
- BS_LEFT constant [MFC]
- BS_ICON constant [MFC]
- BS_TOP constant [MFC]
- BS_TEXT constant
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 18ad3454ddf4d1286d0ba608c3a25d05959de14d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="button-styles"></a>Düğme Stilleri
Bu konu, düğme türleri ve stiller açıklar.  
  
## <a name="button-types"></a>Düğme türleri  
 Aşağıdaki tabloda düğmesi türlerini listeler. İsteğe bağlı olarak aşağıdakilerden birini seçebilirsiniz. Düğme türü belirtmezseniz, varsayılan değer `BS_PUSHBUTTON`.  
  
|Tür|Açıklama|  
|----------|-----------------|  
|`BS_3STATE`|Bir onay kutusu düğmesi ile üç durumdan oluşturur: `BST_CHECKED`, `BST_INDETERMINATE`, ve `BST_UNCHECKED`. Düğmesini tıklatarak gönderir bir `BN_CLICKED` bildirim sahibi penceresine düğmenin durumunu değiştirmez ancak. Varsayılan olarak, onay kutusunun sağında ilişkili metin görüntülenir. Metin kutusunun sol tarafındaki onay için görüntülenecek kullanmak `BS_LEFTTEXT` veya `BS_RIGHTBUTTON` stili.|  
|`BS_AUTO3STATE`|Bir onay kutusu düğmesi ile üç durumdan oluşturur: `BST_CHECKED`, `BST_INDETERMINATE`, ve `BST_UNCHECKED`. Düğmesini tıklatarak gönderir bir `BN_CLICKED` sahibi penceresine bildirim ve düğmesi durumunu değiştirir. Düğme durumları döngüsü sırasına göre `BST_CHECKED`, `BST_INDETERMINATE`, ve `BST_UNCHECKED`. Varsayılan olarak, onay kutusunun sağında ilişkili metin görüntülenir. Metin kutusunun sol tarafındaki onay için görüntülenecek kullanmak `BS_LEFTTEXT` veya `BS_RIGHTBUTTON` stili.|  
|`BS_AUTOCHECKBOX`|Bir onay kutusu düğmesi ile iki durumlu oluşturur: `BST_CHECKED` ve `BST_UNCHECKED`. Düğmesini tıklatarak gönderir bir `BN_CLICKED` sahibi penceresine bildirim ve düğmesi durumunu değiştirir. Varsayılan olarak, onay kutusunun sağında ilişkili metin görüntülenir. Metin kutusunun sol tarafındaki onay için görüntülenecek kullanmak `BS_LEFTTEXT` veya `BS_RIGHTBUTTON` stili.|  
|`BS_AUTORADIOBUTTON`|İki durumlu ile radyo düğmesi oluşturur: `BST_CHECKED` ve `BST_UNCHECKED`. Genellikle radyo düğmeleri gruplarıyla her gruba aynı anda bir checked seçeneği maksimum kullanılır. Düğmesini tıklatarak gönderir bir `BN_CLICKED` bildirim sahibi penceresine ayarlar için tıklatılan radyo düğmesi durumunu `BST_CHECKED`ve diğer tüm radyo düğmeleri durumlarını düğmesi grubuna ayarlar `BST_UNCHECKED`. Varsayılan olarak, ilişkili metin radyo düğmesinin sağında görüntülenir. Metni sola radyo düğmesinin görüntülemek için kullanın `BS_LEFTTEXT` veya `BS_RIGHTBUTTON` stili.|  
|`BS_CHECKBOX`|Bir onay kutusu düğmesi ile iki durumlu oluşturur: `BST_CHECKED` ve `BST_UNCHECKED`. Düğmesini tıklatarak gönderir bir `BN_CLICKED` bildirim sahibi penceresine düğmenin durumunu değiştirmez ancak. Varsayılan olarak, onay kutusunun sağında ilişkili metin görüntülenir. Metin kutusunun sol tarafındaki onay için görüntülenecek kullanmak `BS_LEFTTEXT` veya `BS_RIGHTBUTTON` stili.|  
|`BS_COMMANDLINK`|Bir komut bağlantı düğmesi oluşturur. Komut düğmesi için özel bir komut bağı düğmesini olduğu [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] ana metni ve ana metni altındaki notta solundaki yeşil bir ok görüntüler. Not metnini kullanarak ayarlayabilirsiniz [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote).|  
|`BS_DEFCOMMANDLINK`|Bir komut bağlantı düğmesi oluşturur. Komut düğmesi için özel bir komut bağı düğmesini olduğu [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] ana metni ve ana metni altındaki notta solundaki yeşil bir ok görüntüler. Not metnini kullanarak ayarlayabilirsiniz [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote). Düğmeyi iletişim kutusunda, gönderir anahtar ENTER tuşuna basarak bir `BN_CLICKED` bildirim bile düğmesi giriş odağını olmadığında iletişim kutusu.|  
|`BS_DEFPUSHBUTTON`|Yoğun bir siyah kenarlığa sahip bir komut düğmesi oluşturur. Düğmeyi iletişim kutusunda, gönderir anahtar ENTER tuşuna basarak bir `BN_CLICKED` bildirim bile düğmesi giriş odağını olmadığında iletişim kutusu.|  
|`BS_DEFSPLITBUTTON`|Bölünmüş düğme oluşturur. Bölünmüş düğme için belirli bir komut düğmesi olup [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] için aşağı açılan okunu bitişik bir düğme içerir. Düğmeye tıkladığınızda, varsayılan komutu yürütülür. Aşağı açılan oku tıklatın, ek komutlar menüsü görüntülenir. Bölünmüş düğme iletişim kutusunda, gönderir anahtar ENTER tuşuna basarak bir `BN_CLICKED` bildirim bile düğmesi giriş odağını olmadığında iletişim kutusu|  
|`BS_GROUPBOX`|Diğer düğmeleri gruplandırılabilir Dikdörtgen oluşturur. Bu stili ile ilişkili metin dikdörtgenin sol üst köşesinde görüntülenir.|  
|`BS_OWNERDRAW`|Sahip tarafından çizilmiş düğmesi oluşturur. Framework çağrıları `DrawItem` yöntemi düğmenin görsel yönü zaman değişti. Kullandığınızda bu stili ayarlanmalıdır `CBitmapButton` sınıfı.|  
|`BS_PUSHBUTTON`|Gönderen bir komut düğmesi oluşturur bir `BN_CLICKED` kullanıcı düğmesini tıklattığında sahibi penceresine bildirim.|  
|`BS_RADIOBUTTON`|İki durumlu ile radyo düğmesi oluşturur: `BST_CHECKED` ve `BST_UNCHECKED`. Genellikle radyo düğmeleri gruplarıyla her gruba aynı anda bir checked seçeneği maksimum kullanılır. Düğmesini tıklatarak gönderir bir `BN_CLICKED` bildirim sahibi penceresine otomatik olarak grubundaki herhangi bir düğmeye durumunu değiştirmez ancak. Varsayılan olarak, ilişkili metin radyo düğmesinin sağında görüntülenir. Metni sola radyo düğmesinin görüntülemek için kullanın `BS_LEFTTEXT` veya `BS_RIGHTBUTTON` stili.|  
|`BS_SPLITBUTTON`|Bölünmüş düğme oluşturur. Bölünmüş düğme için belirli bir komut düğmesi olup [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] için aşağı açılan okunu bitişik bir düğme içerir. Düğmeye tıkladığınızda, varsayılan komutu yürütülür. Aşağı açılan oku tıklatın, ek komutlar menüsü görüntülenir.|  
|`BS_USERBUTTON`|16 bit Windows sürümleri ile uyumluluk için sağlanan ancak Kullanımdan kalktı. Win32 tabanlı uygulamalar kullanması gereken `BS_OWNERDRAW` yerine.|  
  
## <a name="radio-button-and-check-box-styles"></a>Radyo düğmesini seçin ve onay kutusu stilleri  
 Aşağıdaki tabloda radyo düğmeleri ve onay kutularını özel stiller listeler. Bu stiller tüm diğer düğmesi türlerinde göz ardı edilir. İsteğe bağlı olarak, bir veya daha fazlasını seçebilirsiniz.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|Radyo düğmesini veya onay kutusunu stili ile birleştirildiğinde, metin radyo düğmesini veya onay kutusunun sol tarafında görünür.|  
|`BS_RIGHTBUTTON`|Radyo düğmesini veya onay kutusunu stili ile birleştirildiğinde, metin radyo düğmesini veya onay kutusunun sol tarafında görünür. Bu stili aynıdır `BS_LEFTTEXT` stili.|  
|`BS_PUSHLIKE`|Bir onay kutusu veya arayın ve komut düğmesi gibi davranır radyo düğmesi hale getirir. Durumu olduğunda basılı düğmesinin `BST_CHECKED`basılı ve durumuna olduğunda soluk `BST_INDETERMINATE`ve durumunu serbest `BST_UNCHECKED`.|  
  
## <a name="text-alignment-styles"></a>Metin hizalama stilleri  
 Aşağıdaki tabloda yatay ve dikey metin hizalama seçeneklerini listeler. İsteğe bağlı olarak aşağıdakilerden birini seçebilirsiniz.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`BS_LEFT`|Sol düğmesi dikdörtgeni metinde hizalar. Ancak, düğme bir onay kutusu veya radyo düğmesi yoktur `BS_RIGHTBUTTON` metin stili değişmeden onay kutusu veya radyo düğmesi sağ tarafta hizalı.|  
|`BS_RIGHT`|Sağa düğmesi dikdörtgeni metinde hizalar. Ancak, düğme bir onay kutusu veya radyo düğmesi yoktur `BS_RIGHTBUTTON` stil, metnin sağ tarafında onay kutusu veya radyo düğmesi sağ hizalanır.|  
|`BS_CENTER`|Düğmesini dikdörtgeni metinde yatay olarak toplanır.|  
|`BS_TOP`|Metin düğmesi dikdörtgenin üst kısmında yerleştirir.|  
|`BS_BOTTOM`|Metin düğmesi Dikdörtgen sonunda yerleştirir.|  
|`BS_VCENTER`|Düğme dikdörtgen dikey metinde toplanır.|  
  
## <a name="button-content-options"></a>Düğme içerik seçenekleri  
 Aşağıdaki tabloda düğmesini görüntülenenleri belirtmek seçeneklerini listeler. Yalnızca metni görüntüle düğmesi türleri bu yoksay. İsteğe bağlı olarak aşağıdakilerden birini seçebilirsiniz.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`BS_BITMAP`|Düğme bir bit eşlem görüntüler belirtir.|  
|`BS_ICON`|Düğme bir simge görüntülenir belirtir.|  
|`BS_TEXT`|Düğme metni görüntüleyen belirtir.|  
  
## <a name="other-options"></a>Diğer seçenekleri  
 Herhangi bir düğme türü ile kullanabileceğiniz ek seçenekleri aşağıdaki tabloda listelenmektedir. İsteğe bağlı olarak, bir veya daha fazlasını seçebilirsiniz.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`BS_FLAT`|Düğme iki boyutlu ve üç boyutlu bir görüntü oluşturmak için varsayılan gölgelendirme ile çizilmiş değil belirtir.|  
|`BS_MULTILINE`|Metin dizesini düğmesi dikdörtgenin içindeki tek bir satırda uymak için çok büyük ise, çok satırlı düğmesi metni sarmalar.|  
|`BS_NOTIFY`|Gönderilecek bir düğmesini etkinleştirir `BN_DBLCLK`, `BN_KILLFOCUS`, ve `BN_SETFOCUS` kendi üst penceresi bildirim iletileri. Gönderme düğmeleri Not `BN_CLICKED` bu stili belirtilip bağımsız olarak bildirim.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC tarafından kullanılan stiller](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../../mfc/reference/cbutton-class.md#create) [düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775951)   



