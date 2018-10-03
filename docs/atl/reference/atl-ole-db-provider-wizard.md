---
title: ATL OLE DB sağlayıcısı Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
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
ms.openlocfilehash: 6857bf80aaaad36b4dcfc4fbf1330eccd03f971a
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250360"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB sağlayıcısı Sihirbazı

Bu sihirbaz, OLE DB sağlayıcısı oluşturma sınıfları oluşturur.

> [!WARNING]
> Visual Studio 2017 sürüm 15.9 bu kod Sihirbazı kullanım dışıdır ve Visual Studio'nun gelecekteki bir sürümde kaldırılacak. Bu sihirbaz nadiren kullanılır. ATL ve MFC genel desteği, bu sihirbazın kaldırma işlemi etkilenmez. Bu kullanımdan kaldırma hakkındaki görüşlerinizi paylaşmak istiyorsanız, Lütfen tamamlayın [bu anketi](https://www.surveymonkey.com/r/QDWKKCN). Geri bildiriminiz bizim için önemlidir.


## <a name="remarks"></a>Açıklamalar

Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betiği altında COM bileşenlerini kaydolacak **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

ATL OLE DB sağlayıcısı Sihirbazı seçenekleri aşağıdaki tabloda açıklanmaktadır:

- **Kısa ad**

   Oluşturulacak sağlayıcının kısa adını yazın. Otomatik olarak doldurur sihirbazdaki diğer düzenleme kutuları Buraya yazdığınız üzerinde temel. Dilerseniz diğer ad kutularını düzenleyebilirsiniz.

- **Coclass'ı**

   Coclass adı. Program Kimliği adı, bu adla eşleşecek şekilde değiştirilir.

- **Öznitelikli**

   Bu seçenek, sihirbaz öznitelikler veya şablon bildirimleri kullanarak sağlayıcısı sınıfları oluşturacak olup olmadığını belirtir. Bu seçeneği belirlediğinizde sihirbaz (öznitelikli projesinde oluşturduysanız varsayılan seçenek budur) şablon bildirimleri yerine öznitelikleri kullanır. Bu seçeneği temizleyin, sihirbaz şablon bildirimleri yerine öznitelikleri (öznitelikli projenizi oluşturduysanız varsayılan seçenek budur) kullanır.

   Öznitelikli olmayan bir proje oluşturduğunuzda bu seçeneği seçerseniz, sihirbaz proje öznitelikli projesinde dönüştürülür ve devam edilip edilmeyeceğini ister uyarır.

- **ProgID**

   Program Kimliği veya programlama tanımlayıcısı, uygulamanızın GUID yerine kullanabileceğiniz bir metin dizesidir. Program Kimliği adı *Projectname.Coclassname*.

- **Sürüm**

   Sağlayıcınızın sürüm numarası. Varsayılan değer 1'dir.

- **Veri kaynağı sınıfı**

   Veri kaynağı sınıfı C formun adını*Shortname*kaynak.

- **Veri kaynağı .h dosyası**

   Veri kaynağı sınıfı için üst bilgi dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Oturum sınıfı**

   Oturum sınıfının C formu adını*Shortname*oturumu.

- **Oturumu .h dosyası**

   Oturum sınıfı için üst bilgi dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Komut sınıfı**

   Komut sınıfının C formun adı*Shortname*komutu.

- **Komut .h dosyası**

   Komut sınıfı için üst bilgi dosyası. Bu ad düzenlenemez ve satır kümesi üst bilgi dosyasının adına bağlıdır.

- **Satır kümesi sınıfı**

   Satır kümesi sınıfının C formun adı*Shortname*satır kümesi.

- **Satır kümesi .h dosyası**

   Satır kümesi sınıfı için üst bilgi dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Satır kümesi .cpp dosyası**

   Sağlayıcının uygulama dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir uygulama dosyasını seçebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL OLE DB sağlayıcısı](../../atl/reference/adding-an-atl-ole-db-provider.md)

