---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 6adfbdc59b2a63aa2f2bb39e27139ca977ba9465
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298759"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , DIĞER tüm com arabiriminin temel arabirimidir.  Bu arabirim üç yöntemi tanımlar: [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)), [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) , bir arabirim kullanıcısına, arayüzünden başka bir işaretçi için nesne sormasını sağlar. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) arabirim üzerinde başvuru sayma uygular.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[IUnknown ve Arabirim devralma](/windows/win32/com/iunknown-and-interface-inheritance)
