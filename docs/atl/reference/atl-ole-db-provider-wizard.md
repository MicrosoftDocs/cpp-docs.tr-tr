---
title: ATL OLE DB sağlayıcısı Sihirbazı
ms.date: 05/09/2019
helpviewer_keywords:
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
ms.openlocfilehash: 91384d6c61368ee56ed303622e5c1bdfad09bd8a
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65706973"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB sağlayıcısı Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 bulunan ve daha yeni değil.

::: moniker-end

::: moniker range="<=vs-2017"

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

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL OLE DB sağlayıcısı](../../atl/reference/adding-an-atl-ole-db-provider.md)
