---
description: 'Daha fazla bilgi edinin: ATL OLE DB sağlayıcı Sihirbazı'
title: ATL OLE DB Sağlayıcısı Sihirbazı
ms.date: 05/09/2019
helpviewer_keywords:
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
ms.openlocfilehash: 068670205c45c559e8b312d633d715f51a78190d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165348"
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB Sağlayıcısı Sihirbazı

::: moniker range="msvc-160"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından oluşturulan kayıt betiği, COM bileşenlerini **HKEY_LOCAL_MACHINE** yerine **HKEY_CURRENT_USER** altına kaydeder. Bu davranışı değiştirmek için, ATL sihirbazının **tüm kullanıcılar Için kayıt bileşeni** seçeneğini ayarlayın.

Aşağıdaki tabloda ATL OLE DB sağlayıcı Sihirbazı seçenekleri açıklanmaktadır:

- **Kısa ad**

   Oluşturulacak sağlayıcının kısa adını yazın. Sihirbazdaki diğer düzenleme kutuları, yazdığınız alana göre otomatik olarak doldurulur. İsterseniz diğer ad kutularını düzenleyebilirsiniz.

- **Coclass**

   Coclass adı. ProgID adı bu adla eşleşecek şekilde değişir.

- **İlişkilendirilmesi**

   Bu seçenek, sihirbazın öznitelikler veya şablon bildirimleri kullanarak sağlayıcı sınıfları oluşturup oluşturmayacağını belirtir. Bu seçeneği belirlediğinizde, sihirbaz şablon bildirimleri yerine öznitelikleri kullanır (öznitelikli bir proje oluşturduysanız bu varsayılan seçenektir). Bu seçeneği temizlediğinizde, sihirbaz öznitelikler yerine şablon bildirimleri kullanır (Bu, öznitelik olmayan bir proje oluşturduysanız bu varsayılan seçenektir).

   Öznitelik atanmış olmayan bir proje oluşturduğunuzda bu seçeneği belirlerseniz, sihirbaz, projenin öznitelikli bir projeye dönüştürüleceğini ve devam edip etmediğini istemediğinizi uyarır.

- **ProgID**

   ProgID veya programlı tanımlayıcı, uygulamanızın GUID yerine kullanabileceği bir metin dizesidir. ProgID adı *ProjectName. Coclassname* biçiminde bulunur.

- **Sürüm**

   Sağlayıcınızın sürüm numarası. Varsayılan değer 1'dir.

- **DataSource sınıfı**

   C *ShortName* kaynağının form veri kaynağı sınıfının adı.

- **DataSource. h dosyası**

   Veri kaynağı sınıfı için üst bilgi dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Oturum sınıfı**

   C *ShortName* oturumunun biçimindeki oturum sınıfının adı.

- **Session. h dosyası**

   Oturum sınıfı için üst bilgi dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Komut sınıfı**

   C *ShortName* komutunun form komut sınıfının adı.

- **Command. h dosyası**

   Komut sınıfı için üst bilgi dosyası. Bu ad düzenlenemiyor ve satır kümesi üstbilgi dosyasının adına bağlı.

- **Rowset sınıfı**

   C *ShortName* satır kümesinin form satır kümesi sınıfının adı.

- **Rowset. h dosyası**

   Satır kümesi sınıfı için üst bilgi dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Rowset. cpp dosyası**

   Sağlayıcının uygulama dosyası. Bu dosyanın adını düzenleyebilir veya var olan bir uygulama dosyasını seçebilirsiniz.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL OLE DB sağlayıcısı](../../atl/reference/adding-an-atl-ole-db-provider.md)
