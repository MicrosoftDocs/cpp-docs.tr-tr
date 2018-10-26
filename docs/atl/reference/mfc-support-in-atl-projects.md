---
title: ATL projelerinde MFC desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.addmfc
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad9e55fa296b8a39e4c77ab33240c837b6c871ea
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063503"
---
# <a name="mfc-support-in-atl-projects"></a>ATL projelerinde MFC desteği

Seçerseniz **destek MFC** ATL Proje Sihirbazı'nda uygulamayı bir MFC uygulaması nesne (sınıfı) olarak projenize bildirir. Proje MFC Kitaplığı başlatır ve bir sınıf oluşturur (sınıfı *ProjName*) sınıfından türetilen [CWinApp](../../mfc/reference/cwinapp-class.md).

Bu seçenek yalnızca nonattributed ATL DLL projelerinde kullanılabilir.

```
class CProjNameApp : public CWinApp
{
public:

// Overrides
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)
END_MESSAGE_MAP()

CProjNameApp theApp;

BOOL CProjNameApp::InitInstance()
{
    return CWinApp::InitInstance();

}

int CProjNameApp::ExitInstance()
{
    return CWinApp::ExitInstance();

}
```

Uygulama nesnesi sınıfı görüntüleyebilir ve `InitInstance` ve `ExitInstance` Sınıf Görünümü'nde işlevleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

