---
title: ATL projelerinde MFC desteği
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 0aece6805f1de987b0164f405e50b99fd706fef4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275431"
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

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)
