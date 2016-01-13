**Clean Web API Docs**
----
  Clean Web by Wise is the world's most advanced real-time content moderation service.
  
  99.9% accuracy, responses within 1 second, available 24/7.
  
  Don't believe us, try it live today.


```bash
curl http://cleanweb.gowise.co/v1/images \
  -u 'test_GD3tvA5sgU3dWID456G': \
  -d image='http://i.imgur.com/mYsghZF.png'
```

---

**DOCUMENTATION**

**POST** [http://cleanweb.gowise.co/v1/images](http://cleanweb.gowise.co/v1/images)

**HEADER**: 

* Authorization: Basic APIKEY
* Content-Type: application/json

**BODY**:

```
{
  "id": "image_identifier" (optional),
  "image": "link_to_image"
}
```
**RESPONSE**:

```
{
  "id": "image_identifier or generated uuid",
  "adult": true|false,
  "adult_score": [0-1],
  "racy": true|false,
  "racy_score": [0-1],
  "graphic": true|false,
  "graphic_score": [0-1],
}
```
**With Metadata:**

Any valid JSON metadata can be passed to train our machine learning models to increase precision

```
{
  "id": "image_identifier" (optional),
  "image": "link_to_image",
  "meta": {
    "follower_count": 10,
    "following_count": 50,
    "karma": 15
  }
}
```