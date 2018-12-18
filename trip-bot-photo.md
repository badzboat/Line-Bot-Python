## Trip bot photo
# 1) Resize photo to 1024x1024 by using   
https://www.befunky.com

# 2) Post photo on AWS S3  
https://console.aws.amazon.com/s3/buckets

# 3) Run "ngrok http 8000"

# 4) Run photo-bot.py
 - Type "Bot"
 - Select album
 
# Location sends as text
# <Location sends as text>
		location_message = LocationSendMessage(type='Where is Mom?', title='Mom home', address='Mom', latitude=13.799750, longitude=100.641546)
		line_bot_api.reply_message(event.reply_token, location_message)	
  
# Image Carousel send as template
# <Image Carousel send as template>
        carousel_template = CarouselTemplate(columns=[
            CarouselColumn(
				thumbnail_image_url='https://s3-us-west-2.amazonaws.com/awsrobomakerhelloworld-154344673743-bundlesbucket-1n2aine7xqbt8/image/miyuu1024-1.jpg',
				text='Miyuu#1',
				actions=[
					PostbackAction(
						label='Best Friend',
						text='Elvis',
						data='Elvis'
					)
				]	
        ),
            CarouselColumn(
				thumbnail_image_url='https://s3-us-west-2.amazonaws.com/awsrobomakerhelloworld-154344673743-bundlesbucket-1n2aine7xqbt8/image/miyuu1024-2.jpg',
				text='Miyuu#2',
				actions=[
					PostbackAction(
						label='GreatWolfLodge',
						text='Water park',
						data='Water park'
					)
				]	
        ),  
            CarouselColumn(
				thumbnail_image_url='https://s3-us-west-2.amazonaws.com/awsrobomakerhelloworld-154344673743-bundlesbucket-1n2aine7xqbt8/image/miyuu1024-3.jpg',
				text='Miyuu#3',
				actions=[
					PostbackAction(
						label='Miyuu Cycle',
						text='Arcade',
						data='Arcade'
					)
				]	
		),
            CarouselColumn(
				thumbnail_image_url='https://s3-us-west-2.amazonaws.com/awsrobomakerhelloworld-154344673743-bundlesbucket-1n2aine7xqbt8/image/miyuu1024-4.jpg',
				text='Miyuu#4',
				actions=[
					PostbackAction(
						label='Bath Time',
						text='Love It',
						data='Love It'
					)
				]	
		),		
            CarouselColumn(
				thumbnail_image_url='https://s3-us-west-2.amazonaws.com/awsrobomakerhelloworld-154344673743-bundlesbucket-1n2aine7xqbt8/image/miyuu1024-5.jpg',
				text='Miyuu#5',
				actions=[
					PostbackAction(
						label='The Gang',
						text='The Gang',
						data='The Gang'
					)
				]	
        )])
        template_message = TemplateSendMessage(
            alt_text='Carousel alt text', template=carousel_template)
        line_bot_api.reply_message(event.reply_token, template_message)
