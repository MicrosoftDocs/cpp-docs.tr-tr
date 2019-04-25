---
title: Dizeleri OLE DB Sağlayıcısına Okuma
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: d46b4e1a53e7e489763f40e7a5238e65b493f7c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283863"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısına Okuma

`CCustomRowset::Execute` İşlevi bir dosyayı açar ve dizelerini okur. Tüketici dosya adı çağırarak sağlayıcıya geçen [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)). Sağlayıcı dosya adını alır ve üye değişkeni depolar `m_strCommandText`. `Execute` Dosya adından okur `m_strCommandText`. Dosya adı geçersiz veya dosya kullanılamıyor `Execute` bir hata döndürür. Aksi takdirde, çağrılar ve dosyayı açar `fgets` dizeleri alınamadı. Her dizeleri okuma ayarlayın `Execute` kullanıcı kaydını örneği oluşturur (değiştirilmiş `CCustomWindowsFile` gelen [dizeleri OLE DB sağlayıcısı depolama](../../data/oledb/storing-strings-in-the-ole-db-provider.md)) ve bir diziye yerleştirir.

Dosya açılamıyor, `Execute` DB_E_NOTABLE döndürmelidir. Bunun yerine E_FAIL döndürürse, sağlayıcı birçok tüketicileriyle çalışmaz ve OLE DB başarılı olmaz [uygunluk testlerini](../../data/oledb/testing-your-provider.md).

## <a name="example"></a>Örnek

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
{
public:
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
    {
        enum {
            sizeOfBuffer = 256,
            sizeOfFile = MAX_PATH
        };
        USES_CONVERSION;
        FILE* pFile = NULL;
        TCHAR szString[sizeOfBuffer];
        TCHAR szFile[sizeOfFile];
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
            }

            am.dwBookmark = ++cFiles;
            if (!m_rgRowData.Add(am))
            {
                ATLTRACE("Couldn't add data to array");
                fclose(pFile);
                return E_FAIL;
            }
        }

        if (pcRowsAffected != NULL)
            *pcRowsAffected = cFiles;
        return S_OK;
    }
};
```

Sağlayıcınıza bu yapıldığında, derlemek ve çalıştırmak hazır olması gerekir. Sağlayıcıyı test eşleşen işlevselliğe sahip bir tüketici gerekir. [Basit Tüketici Uygulama](../../data/oledb/implementing-a-simple-consumer.md) bu tür bir test tüketici oluşturma işlemi gösterilmektedir. Test müşteri ve sağlayıcı ile çalıştırmak ve test tüketici sağlayıcıdan doğru dizeleri alır doğrulayın.

Sağlayıcınız başarıyla test ettikten sonra ek arabirimlerini uygulayarak işlevselliğini artırmak isteyebilirsiniz. Bir örnek gösterilmiştir [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).

## <a name="see-also"></a>Ayrıca bkz.

[Basit Salt Okunur Sağlayıcıyı Uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
