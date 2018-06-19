---
title: ATL OLE DB Sağlayıcı Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.provider.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 827b46de299341f23d0b799a5ed44b8923bbc182
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357486"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB Sağlayıcı Sihirbazı
Bu sihirbaz bir OLE DB sağlayıcısı oluşturma sınıfları oluşturur.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betik COM bileşenlerini altında kaydedeceksiniz **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için ayarlanmış **kayıt bileşeni tüm kullanıcılar için** ATL Sihirbazı'nın seçeneği.  
  
 Aşağıdaki tabloda ATL OLE DB Sağlayıcı Sihirbazı için seçenekleri açıklar:  
  
 **Kısa ad**  
 Oluşturulacak sağlayıcısının kısa adı yazın. Sihirbazın diğer düzenleme kutusuna otomatik olarak doldurulması Buraya yazdığınız üzerinde temel. İsterseniz diğer ad kutularını düzenleyebilirsiniz.  
  
 **coclass'ı**  
 Coclass'ı adı. ProgID adı, bu adla eşleşecek şekilde değiştirilir.  
  
 **Öznitelikli**  
 Bu seçenek, sihirbaz öznitelikleri veya şablon bildirimleri kullanarak sağlayıcısı sınıfları oluşturacak olup olmadığını belirtir. Bu seçeneği seçtiğinizde, sihirbaz öznitelikleri yerine şablon bildirimleri (öznitelikli projesinde oluşturduysanız varsayılan seçenek budur) kullanır. Bu seçeneği temizleyin Sihirbazı'nı (öznitelikli proje oluşturduysanız varsayılan seçenek budur) öznitelikler yerine şablon bildirimleri kullanır.  
  
 Öznitelikli olmayan bir proje oluşturduğunuzda bu seçeneği seçerseniz, sihirbazın proje öznitelikli projesinde dönüştürülür ve devam edilip edilmeyeceğini soran uyarır.  
  
 **ProgID**  
 ProgID ya da program tanımlayıcısı, uygulamanızı bir GUID yerine kullanabileceğiniz bir metin dizesidir. Formun ProgID adına sahip *Projectname.Coclassname*.  
  
 **Sürüm**  
 Sağlayıcınız sürüm numarası. Varsayılan değer 1'dir.  
  
 **Veri kaynağı sınıfı**  
 Veri kaynağı sınıfı, C formun adını*kısaad*kaynak.  
  
 **Veri kaynağı .h dosyası**  
 Veri kaynağı sınıfı için üstbilgi dosyası. Bu dosyanın adını düzenleyin veya varolan bir üstbilgi dosyası seçin.  
  
 **Oturum sınıfı**  
 C formunun oturum sınıfın adını*kısaad*oturumu.  
  
 **Oturum .h dosyası**  
 Oturum sınıfı için üstbilgi dosyası. Bu dosyanın adını düzenleyin veya varolan bir üstbilgi dosyası seçin.  
  
 **Komut sınıfı**  
 C formunun komutu sınıfın adını*kısaad*komutu.  
  
 **Komut .h dosyası**  
 Komut sınıfı için üstbilgi dosyası. Bu ad düzenlenemez ve satır kümesi üstbilgi dosyası adına bağlıdır.  
  
 **Satır kümesi sınıfı**  
 C formunun satır kümesi sınıfın adını*kısaad*satır kümesi.  
  
 **Satır kümesi .h dosyası**  
 Satır kümesi sınıfı için üstbilgi dosyası. Bu dosyanın adını düzenleyin veya varolan bir üstbilgi dosyası seçin.  
  
 **Satır kümesi .cpp dosyası**  
 Sağlayıcının uygulama dosyası. Bu dosyanın adını düzenleyin veya varolan bir uygulama dosya seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL OLE DB sağlayıcısı](../../atl/reference/adding-an-atl-ole-db-provider.md)

