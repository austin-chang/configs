Mimo

    [rewrite_local]
    ^https:\/\/api\.getmimo\.com\/v1\/subscriptions$ url script-response-body mimo.vip.js
    
    hostname = api.getmimo.com

Musixmatch

    [rewrite_local]
	^https:\/\/apic\.musixmatch\.com\/ws\/.*\/config\.get url script-response-body musixmatch.miao.js
	
	hostname = apic.musixmatch.com
    
Netflix Rating

    [rewrite_local]
    ^https?://ios\.prod\.ftl\.netflix\.com/iosui/user/.+path=%5B%22videos%22%2C%\d+%22%2C%22summary%22%5D url script-request-header nf_rating.js
    ^https?://ios\.prod\.ftl\.netflix\.com/iosui/user/.+path=%5B%22videos%22%2C%\d+%22%2C%22summary%22%5D url script-response-body nf_rating.js
    
    hostname = ios.prod.ftl.netflix.com

Browse TikTok with Chinese carrier

    [rewrite_local]
    (?<=(carrier|sys)_region=)CN url 307 US
    (?<=version_code=)\d{1,}.\d{1}\.\d{1} url 307 14.0.0
    
    hostname = api*.tiktokv.com, api*.musical.ly, api*.amemv.com, aweme*.snssdk.com