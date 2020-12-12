---
description: 'Daha fazla bilgi edinin: basit bir Read-Only sağlayıcı oluşturma'
title: Basit bir Salt Okunur Sağlayıcı Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: 1904e850bc6a681e13e4799a2822963932ad9dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323226"
---
# <a name="creating-a-simple-read-only-provider"></a>Basit bir Salt Okunur Sağlayıcı Oluşturma

::: moniker range="msvc-160"

ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

**Atl Proje Sihirbazı** ve **ATL OLE DB sağlayıcı Sihirbazı 'nı** kullanarak bir OLE DB sağlayıcısı oluşturduğunuzda, desteklemek istediğiniz diğer işlevleri ekleyebilirsiniz. Tüketiciye ne tür verilerin ve hangi koşullarda gönderdiklerinizi inceleyerek sağlayıcınızı tasarlamaya başlayın. Komutları, işlemleri ve diğer isteğe bağlı nesneleri desteklemek isteyip istemediğinizi öğrenmek özellikle önemlidir. İyi bir tasarım, uygulama ve test hızını hızlandıracaktır.

Örnek iki bölümde sunulmaktadır:

- İlk bölüm, bir çift dizeyi okuyan [basit bir salt okunur sağlayıcının nasıl oluşturulacağını](../../data/oledb/implementing-the-simple-read-only-provider.md) gösterir.

- İkinci bölüm, arabirimi ekleyerek [basit salt okuma sağlayıcısının nasıl geliştirileceğini](../../data/oledb/enhancing-the-simple-read-only-provider.md) gösterir `IRowsetLocate` .

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
